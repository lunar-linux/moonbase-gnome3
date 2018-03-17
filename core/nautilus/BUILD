mkdir -p build &&
 
OPTS+=" --prefix /usr \
        -Ddocs=false \
        -Dselinux=false \
        -Denable-extensions=false"

meson build $OPTS &&

ninja -C build &&

prepare_install &&

ninja -C build install
