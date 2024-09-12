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
        -D USE_SOUP2=OFF                \
        -D USE_SYSTEM_MALLOC=ON         \
        -D ENABLE_BUBBLEWRAP_SANDBOX=ON \
        -D ENABLE_UNIFIED_BUILDS=OFF    \
        -W no-dev"

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
