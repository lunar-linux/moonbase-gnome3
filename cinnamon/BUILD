sedit "s:--warn-all --warn-error::" src/Makefile.am  &&

sedit "s:gnome-autogen.sh:.\/gnome-autogen.sh:" autogen.sh  &&

chmod +x gnome-autogen.sh &&

./autogen.sh --prefix=/usr                  \
             --sysconfdir=/etc              \
             --libexecdir=/usr/lib/cinnamon \
             --localstatedir=/var           \
             --disable-static               \
             --enable-compile-warnings=no   \
             $OPTS                         &&

sedit "s:-Werror:-W :" src/Makefile  &&

default_make
