./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --libexecdir=/usr/lib/cinnamon \
             --localstatedir=/var \
             --disable-static \
             --disable-schemas-compile \
             --enable-compile-warnings=no \
             $OPTS &&

sedit "s:-Werror:-W :" Makefile &&

default_make
