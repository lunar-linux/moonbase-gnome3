mkdir -p build &&

OPTS+=" --prefix /usr -Denable_docs=false"

meson build $OPTS &&

ninja -C build &&

prepare_install &&

ninja -C build install &&

install -m0644 $SCRIPT_DIRECTORY/61-gnome-bluetooth-rfkill.rules /usr/lib/udev/rules.d/
