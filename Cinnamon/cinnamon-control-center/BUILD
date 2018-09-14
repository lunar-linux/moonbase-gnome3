sedit "s:subdir-objects::g" configure.ac &&

OPTS+=" --prefix=/usr \
        --sysconfdir=/etc \
        --localstatedir=/var \
        --disable-wacom \
        --disable-static \
        --disable-onlineaccounts \
        --enable-compile-warnings=no"

if ! module_installed cupd; then
   OPTS+=" --disable-cups"
fi

./autogen.sh $OPTS &&

#sedit "s:-Werror:-W :" Makefile &&

default_build
