sedit "s:subdir-objects::g" configure.ac &&

./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             --enable-compile-warnings=no \
             $OPTS &&


sedit "s:-Werror:-W :" Makefile &&

default_make
