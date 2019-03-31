OPTS+=" --enable-ipv6 \
        --enable-gdm-session \
        --disable-static \
        --without-plymouth \
        --without-console-kit \
        --without-tcp-wrappers \
        --disable-schemas-compile"

if module_installed systemd; then
   OPTS+=" --enable-systemd-journal"
fi

default_build
