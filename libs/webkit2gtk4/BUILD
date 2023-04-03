OPTS+=" -DPORT=GTK \
        -DUSE_GTK4=ON \
        -DUSE_SOUP2=OFF \
        -DCMAKE_VERBOSE_MAKEFILE=ON \
        -DENABLE_INTROSPECTION=ON \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_SKIP_RPATH=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBDIR=lib  \
        -DCMAKE_INSTALL_LIBEXECDIR=lib \
        -DENABLE_MINIBROWSER=ON \
        -DENABLE_DOCUMENTATION=OFF"

cmake -B $MODULE-$VERSION -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&
prepare_install &&
cmake --install $MODULE-$VERSION &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
  ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
