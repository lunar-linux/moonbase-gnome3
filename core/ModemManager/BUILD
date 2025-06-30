export LANG='en_US.UTF-8'

if in_depends $MODULE systemd ; then
  OPTS+=" -Ddbus_policy_dir=/usr/share/dbus-1/system.d \
          -Dsystemd_journal=true \
          -Dsystemd_suspend_resume=true"
fi &&

OPTS+=" -Dpolkit=permissive \
        -Dudevdir=/usr/lib/udev \
        -Dvapi=true"

default_meson_build
