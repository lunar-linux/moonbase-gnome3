OPTS+=" -DENABLE_MINIBROWSER=ON \
        -DENABLE_WEBKIT_LEGACY=OFF \
        -DENABLE_PLUGIN_PROCESS_GTK2=OFF \
        -DUSE_WOFF2=OFF \
        -DPORT=GTK" &&

default_cmake_build &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
  ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
