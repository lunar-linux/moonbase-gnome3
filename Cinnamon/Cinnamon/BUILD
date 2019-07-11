./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             --disable-gtk-doc \
             --disable-schemas-compile \
             --enable-compile-warnings=no \
             $OPTS &&

sedit "s:-Werror:-W :" src/Makefile &&

default_make
