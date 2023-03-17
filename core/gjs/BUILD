OPTS=" -Dinstalled_tests=false"

CFLAGS="${CFLAGS/-O2/-O3} -fno-semantic-interposition"
CXXFLAGS="${CXXFLAGS/-O2/-O3} -fno-semantic-interposition"
LDFLAGS+=" -Wl,-Bsymbolic-functions"

default_meson_build
