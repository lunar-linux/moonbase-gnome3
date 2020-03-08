OPTS+=" -Db_lto=false"

default_meson_build &&

# fix lxterminal with gtk+-3
ln -sf /usr/lib/pkgconfig/vte-2.91.pc /usr/lib/pkgconfig/vte-2.90.pc

# fix termit
ln -sf /usr/include/vte-2.91/vte /usr/include/vte

mv /etc/profile.d/vte.sh /etc/profile.d/vte.rc
