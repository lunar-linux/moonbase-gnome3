OPTS+=" --enable-ipv6 \
        --disable-static \
        --without-plymouth \
        --without-tcp-wrappers \
        --disable-schemas-compile"

if module_installed systemd; then
   OPTS+=" --enable-systemd-journal"
fi

if module_installed wayland; then
   OPTS+=" --enable-wayland-support"
fi &&
OPTS+=" --enable-debug" &&
add_priv_user gdm:gdm &&

default_build
