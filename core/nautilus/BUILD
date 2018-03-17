mkdir -p build &&
 
meson build --prefix /usr \
            -Dselinux=false \
            -Denable_docs=false \
            -Denable-extensions=false &&

ninja -C build &&

prepare_install &&

ninja -C build install
