OPTS+=" --prefix /usr \
        -Denable_docs=false"

default_meson_build &&

install -m0644 $SCRIPT_DIRECTORY/61-gnome-bluetooth-rfkill.rules /usr/lib/udev/rules.d/
