OPTS+=" -DPORT=GTK \
      -DCMAKE_BUILD_TYPE=Release \
      -DCMAKE_SKIP_RPATH=ON \
      -DCMAKE_INSTALL_PREFIX=/usr \
      -DLIB_INSTALL_DIR=/usr/lib \
      -DENABLE_DOCUMENTATION=OFF \
      -DUSE_SOUP2=ON"
## note: soup2 needs to be used, because soup3 requires glibc 2.69
## which we don't have yet

if [[ $MINIBROWSER == "y" ]]; then
  OPTS+=" -DENABLE_MINIBROWSER=ON"
fi &&

cmake -B $MODULE -G Ninja $OPTS &&
cmake --build $MODULE &&
prepare_install &&
cmake --install $MODULE &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
  ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
