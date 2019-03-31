NOCONFIGURE=1 ./autogen.sh &&

if in_depends $MODULE systemd ; then
  OPTS+=" --with-dbus-sys-dir=/usr/share/dbus-1/system.d \
          --with-systemd-journal \
          --with-systemd-suspend-resume"
fi &&

OPTS+=" --disable-static \
        --with-polkit=permissive \
        --with-udev-base-dir=/usr/lib/udev"

default_build
