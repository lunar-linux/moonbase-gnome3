mkdir -p build &&

OPTS+=" --prefix /usr -Denable_docs=false"

meson build $OPTS &&

ninja -C build &&

prepare_install &&

ninja -C build install
