mkdir -p build &&

meson build -Dlibportal=false --prefix /usr &&
ninja -C build &&

prepare_install &&

ninja -C build install
