CFLAGS+=" -Wno-error=implicit-int -Wno-error=incompatible-pointer-types"

sed -i '/AM_INIT_AUTOMAKE/s/]/ foreign]/' configure.ac &&
autoreconf -fvi &&

OPTS+=" --with-xinput=yes --disable-gtk-doc"

default_build
