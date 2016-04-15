OPTS+=" --disable-schemas-compile \
        --disable-desktop-update \
        --disable-icon-update" &&

default_build

install -m0644 $SCRIPT_DIRECTORY/61-gnome-bluetooth-rfkill.rules /usr/lib/udev/rules.d/
