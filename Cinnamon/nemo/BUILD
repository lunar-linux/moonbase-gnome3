./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --localstatedir=/var \
             --disable-static \
             --disable-update-mimedb \
             --disable-tracker \
             --disable-gtk-doc-html \
             --disable-schemas-compile \
             $OPTS  &&

#sedit "s:-Werror:-W :" src/Makefile &&

default_make
