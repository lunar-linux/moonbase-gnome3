#Fix a webassembly regression
sed '/returnLocation.isStackArgument/,/returnLocation = canonicalLocation/d'\
    -i Source/JavaScriptCore/wasm/WasmBBQJIT.cpp &&

CPPFLAGS="-DNDEBUG"

OPTS+=" -D CMAKE_INSTALL_PREFIX=/usr    \
        -D CMAKE_SKIP_INSTALL_RPATH=ON  \
        -D CMAKE_BUILD_TYPE=Release     \
        -D PORT=GTK                     \
        -D LIB_INSTALL_DIR=/usr/lib     \
        -D USE_LIBBACKTRACE=OFF         \
        -D ENABLE_GAMEPAD=OFF           \
        -D ENABLE_MINIBROWSER=ON        \
        -D ENABLE_DOCUMENTATION=OFF     \
        -D USE_GTK4=OFF                 \
        -D USE_SOUP2=ON                 \
        -D USE_SYSTEM_SYSPROF_CAPTURE=NO \
        -W no-dev"

#https://blogs.igalia.com/carlosgc/2024/09/27/graphics-improvements-in-webkitgtk-and-wpewebkit-2-46/
#Skia has received several GCC specific optimizations lately, but it�always always more optimized #when
# built with clang. The optimizations are more noticeable in performance when using the CPU for rendering. 
export CC=clang CXX=clang++
LDFLAGS+=" -fuse-ld=lld"

# Skia uses malloc_usable_size
CFLAGS="${CFLAGS/_FORTIFY_SOURCE=3/_FORTIFY_SOURCE=2}"
CXXFLAGS="${CXXFLAGS/_FORTIFY_SOURCE=3/_FORTIFY_SOURCE=2}"

# JITted code crashes when CET is used
CFLAGS+=' -fcf-protection=none'
CXXFLAGS+=' -fcf-protection=none'

if module_installed systemd; then
  OPTS+=" -D ENABLE_JOURNALD_LOG=ON"
 else
  OPTS+=" -D ENABLE_JOURNALD_LOG=OFF"
fi &&

cmake -B webkitgtk-$VERSION -G Ninja $OPTS &&
cmake --build webkitgtk-$VERSION &&
prepare_install &&
cmake --install webkitgtk-$VERSION &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
  ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
