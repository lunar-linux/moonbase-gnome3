./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             --with-mit-ext \
             $OPTS &&

default_make

# Now the .desktop files
install -Dm 644 {"$SCRIPT_DIRECTORY",/usr/share/applications}/cinnamon-screensaver.desktop
