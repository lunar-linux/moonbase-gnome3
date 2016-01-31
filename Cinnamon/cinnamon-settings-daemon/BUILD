./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --libexecdir=/usr/lib/cinnamon \
             --localstatedir=/var \
             --disable-static \
             $OPTS &&

#             --enable-compile-warnings=no \

sedit "s:-Werror:-W :" Makefile &&

default_make
