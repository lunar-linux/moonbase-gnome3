#default_meson_build

prepare_install &&

meson "build" --prefix=/usr &&
DESTDIR="/" ninja -C "build" install
