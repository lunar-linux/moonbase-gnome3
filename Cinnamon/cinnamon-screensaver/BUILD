patch_it $SOURCE3 1 &&

sedit "s:gnome-autogen.sh:.\/gnome-autogen.sh:" autogen.sh  &&

cp -f $SCRIPT_DIRECTORY/pam.d/cinnamon-screensaver data/  &&

chmod +x gnome-autogen.sh &&

./autogen.sh --prefix=/usr     \
             --sysconfdir=/etc \
             --libexecdir=/usr/lib/cinnamon-screensaver \
             --localstatedir=/var \
             --disable-static \
             --with-mit-ext   \
             --with-systemd   \
             $OPTS           &&

default_make

# Now the .desktop files
install -Dm 644 {"$SCRIPT_DIRECTORY",/usr/share/applications}/cinnamon-screensaver.desktop
install -Dm 644 {"$SCRIPT_DIRECTORY",/usr/share/applications}/cinnamon2d-screensaver.desktop

