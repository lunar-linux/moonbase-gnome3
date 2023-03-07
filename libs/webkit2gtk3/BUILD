OPTS+=" -DPORT=GTK \
      -DCMAKE_VERBOSE_MAKEFILE=ON \
      -DENABLE_INTROSPECTION=ON \
      -DCMAKE_BUILD_TYPE=Release \
      -DCMAKE_SKIP_RPATH=ON \
      -DCMAKE_INSTALL_PREFIX=/usr \
      -DLIB_INSTALL_DIR=/usr/lib \
      -DENABLE_DOCUMENTATION=OFF"

if [[ $MINIBROWSER == "y" ]]; then
  OPTS+=" -DENABLE_MINIBROWSER=ON"
fi &&

cmake -B $MODULE-$VERSION -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&
prepare_install &&
cmake --install $MODULE-$VERSION &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
  ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
