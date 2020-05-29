OPTS+=" -Dtests=no \
        -Dqt=false \
        -Debpf=false \
        -Ddocs=false \
        -Dlibaudit=no \
        -Dselinux=false \
        -Dmore_asserts=no \
        -Dmodify_system=true \
        -Dmore-logging=false \
        -Dfirewalld_zone=false \
        -Dsession_tracking_consolekit=false \
        -Ddbus_conf_dir=/usr/share/dbus-1/system.d"

if module_installed systemd; then
    OPTS+=" -Dsession_tracking=systemd \
            -Dsystemd_journal=true \
            -Dsuspend_resume=systemd \
            -Dconfig_loggin_backend_default=journal \
            -Dsystemdsystemunitdir=/usr/lib/systemd/system"
else
    if module_installed elogind; then
        OPTS+=" -Dsession_tracking=elogind"
    fi
    if module_installed syslog-ng; then
        OPTS+="-Dconfig_loggin_backend_default=syslog"
    fi
fi

default_meson_build