mkdir -p build &&

meson build --prefix /usr &&
ninja -C build &&

prepare_install &&

ninja -C build install
