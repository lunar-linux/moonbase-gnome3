OPTS+=" -DENABLE_MINIBROWSER=1 -DPORT=GTK -DUSE_LD_GOLD=0" &&

default_cmake_build &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
  ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
