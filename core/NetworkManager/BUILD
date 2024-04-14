unset LDFLAGS &&
export LANG='en_US.UTF-8'

OPTS+=" -D tests=no \
        -D qt=false \
        -D ebpf=false \
        -D docs=false \
        -D libaudit=no \
        -D selinux=false \
        -D more_asserts=no \
        -D modify_system=true \
        -D more_logging=false \
        -D firewalld_zone=false \
        -D session_tracking_consolekit=false \
        -D dbus_conf_dir=/usr/share/dbus-1/system.d"

if module_installed systemd; then
    OPTS+=" -D session_tracking=systemd \
            -D systemd_journal=true \
            -D suspend_resume=systemd \
            -D config_logging_backend_default=journal \
            -D systemdsystemunitdir=/usr/lib/systemd/system"
else
    if module_installed elogind; then
        OPTS+=" -D session_tracking=elogind"
    fi
    if module_installed syslog-ng; then
        OPTS+="-D config_logging_backend_default=syslog"
    fi
fi

default_meson_build
