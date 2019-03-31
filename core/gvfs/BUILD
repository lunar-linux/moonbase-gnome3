OPTS+=" -Dgudev=true \
        -Dgoa=false \
        -Dgoogle=false"

if ! ( module_installed systemd ); then
  OPTS+=" -Dsystemduserunitdir=no \
          -Dtmpfilesdir=no
          -Dlogind=false"
fi

default_meson_build
