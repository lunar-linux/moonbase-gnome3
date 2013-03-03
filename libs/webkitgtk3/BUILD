OPTS+=" --with-target=x11             \
        --with-unicode-backend=icu    \
        --with-font-backend=freetype  \
        --enable-xslt                 \
        --enable-optimizations        \
        --disable-glibtest            \
        --with-gtk=3.0                \
        --enable-video                \
        --disable-web-audio           \
        --disable-gtk-doc-html"      &&

#make build work even if gtk-doc is not installed
if ! module_installed gtk-doc ; then
  sed -i '/gtkdoc --rebase/s:^:# :' GNUmakefile.in
fi &&

#stolen from blfs, avoid race condition in build with multiple makes
default_config &&
error_count=0 &&
until default_make
do
  if (( $((error_count++)) > 4 )) ; then
    echo Too Many Errors &&
    break
  fi
done &&
unset error_count &&
make install &&
install 'Programs/GtkLauncher' '/usr/bin/Gtk3Launcher' &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
   ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
