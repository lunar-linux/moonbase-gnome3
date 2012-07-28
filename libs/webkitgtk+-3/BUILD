(


  OPTS+=" --with-target=x11             \
          --with-unicode-backend=icu    \
          --with-font-backend=freetype  \
          --enable-xslt                 \
          --enable-svg-fonts            \
          --enable-optimizations        \
          --with-gtk=3.0                \
          --disable-gtk-doc-html"      &&

  default_build &&

  install 'Programs/GtkLauncher' '/usr/bin/Gtk3Launcher'

) > $C_FIFO 2>&1
