
  patch_it $SOURCE2 1 &&

# breaks without webgl for now
  OPTS+=" --enable-x11-target           \
          --enable-optimizations        \
          --enable-introspection        \
          --disable-glibtest            \
          --enable-video                \
          --enable-webgl                \
          --disable-gtk-doc-html"      &&

#make build work even if gtk-doc is not installed
  if ! module_installed gtk-doc ; then
    sed -i '/gtkdoc --rebase/s:^:# :' GNUmakefile.in
  fi &&

# First we build the gtk3 version sans webkit2
  mkdir build-3 &&
  cp -a Documentation build-3 &&
  cd build-3
  OPTS+=" --with-gtk=3.0 --disable-webkit2" &&
  ../configure --prefix=/usr $OPTS &&
  default_make &&
  install 'Programs/GtkLauncher' '/usr/bin/Gtk3Launcher' &&

# Now if gtk+-2 is in depends we build for it
  if in_depends $MODULE gtk+-2 ; then
    cd ../ &&
    mkdir build-2 &&
    cp -a Documentation build-2 &&
    cd build-2
    OPTS+=" --with-gtk=3.0 --enable-webkit2" &&
    ../configure --prefix=/usr$OPTS &&
    default_make &&
    install 'Programs/GtkLauncher' '/usr/bin/Gtk2Launcher'
  fi &&

  cd ../ &&
# symlink plugin folder to a location webkit looks for it
  if [ ! -e "/usr/lib/browser-plugins" ]; then
     ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
  fi
