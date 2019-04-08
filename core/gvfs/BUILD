if ! ( module_installed systemd ); then
  OPTS+=" -Dsystemduserunitdir=no \
          -Dtmpfilesdir=no
          -Dlogind=false"
fi

default_meson_build
