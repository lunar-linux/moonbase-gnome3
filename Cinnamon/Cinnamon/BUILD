./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             --enable-compile-warnings=no \
             $OPTS &&

sedit "s:-Werror:-W :" src/Makefile &&

default_make
