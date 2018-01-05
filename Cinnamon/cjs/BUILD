./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             $OPTS &&

sedit "s:-Werror:-W :" Makefile &&

default_make
