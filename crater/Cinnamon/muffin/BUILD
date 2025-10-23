./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             --disable-schemas-compile \
             --enable-compile-warnings=minimum \
             $OPTS &&

sedit "s:-Werror:-W :" Makefile &&

default_make
