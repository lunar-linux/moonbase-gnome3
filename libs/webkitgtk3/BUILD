# breaks without webgl for now
OPTS+=" --enable-video         \
        --enable-webgl         \
        --enable-x11-target    \
        --enable-optimizations \
        --enable-introspection \
        --disable-glibtest"

# see webkit2gtk3 module for this
OPTS+=" --disable-webkit2" &&

# make build work even if gtk-doc is not installed
if ! module_installed gtk-doc; then
  sedit '/gtkdoc --rebase/s:^:# :' GNUmakefile.in
fi &&

OLD_OPTS="$OPTS" &&
# First we build the gtk3 version
mkdir build-3 &&
cp -a Documentation build-3 &&
cd build-3 &&
OPTS+=" --with-gtk=3.0" &&
../configure --prefix=/usr $OPTS &&
default_make &&
install 'Programs/GtkLauncher' '/usr/bin/Gtk3Launcher' &&
cd .. &&

# Now if gtk+-2 is install we build for it
if in_depends $MODULE gtk+-2 ; then
  devoke_installwatch &&
  OPTS="$OLD_OPTS" &&
  mkdir build-2 &&
  cp -a Documentation build-2 &&
  cd build-2 &&
  OPTS+=" --with-gtk=2.0" &&
  ../configure --prefix=/usr $OPTS &&
  default_make &&
  install 'Programs/GtkLauncher' '/usr/bin/Gtk2Launcher' &&
  cd ..
fi &&

# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
   ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
