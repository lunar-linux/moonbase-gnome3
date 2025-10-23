./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             $OPTS &&

#             --enable-compile-warnings=no \

sedit "s:-Werror:-W :" Makefile &&

default_make
