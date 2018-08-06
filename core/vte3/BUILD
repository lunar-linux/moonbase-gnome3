OPTS+=" --disable-static"

if [ "`get_module_config DOCS`" = "n" ]; then
  sedit "s/src termcaps po doc perf/src termcaps po perf/g" Makefile.in
fi &&

default_build &&

# fix lxterminal with gtk+-3
ln -sf /usr/lib/pkgconfig/vte-2.91.pc /usr/lib/pkgconfig/vte-2.90.pc

mv /etc/profile.d/vte.sh /etc/profile.d/vte.rc
