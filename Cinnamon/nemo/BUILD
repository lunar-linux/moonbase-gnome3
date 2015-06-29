sed -i '/AC_SUBST(DISABLE_DEPRECATED_CFLAGS)/d' configure.in  &&

#sedit "s:--warn-all --warn-error::" src/Makefile.am  &&

sedit "s:gnome-autogen.sh:.\/gnome-autogen.sh:" autogen.sh  &&

sedit "s:import polib:\#import polib:" data/merge_action_strings  &&

chmod +x gnome-autogen.sh &&

./autogen.sh --prefix=/usr \
             --sysconfdir=/etc \
             --libexecdir=/usr/lib/nemo \
             --localstatedir=/var \
             --disable-static \
             --disable-update-mimedb \
             --disable-tracker \
             --disable-gtk-doc-html \
             --disable-schemas-compile  \
             $OPTS  &&

#sedit "s:-Werror:-W :" src/Makefile  &&

default_make
