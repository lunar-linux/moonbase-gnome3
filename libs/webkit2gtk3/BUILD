OPTS+=" -DPORT=GTK \
        -DUSE_WOFF2=OFF \
        -DCMAKE_SKIP_RPATH=ON \
        -DENABLE_WEBKIT_LEGACY=OFF \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DLIB_INSTALL_DIR=/usr/lib"

if [[ $MINIBROWSER == "y" ]]; then
  OPTS+=" -DENABLE_MINIBROWSER=ON"
fi

if [[ $WPEBACKEND == "y" ]]; then
  OPTS+=" -DUSE_WPE_RENDERER=ON"
else
  OPTS+=" -DUSE_WPE_RENDERER=OFF"
fi

#default_cmake_build &&
cmake $OPTS -G Ninja . &&
ninja -j1 &&

prepare_install &&
ninja -j1 install &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
  ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
