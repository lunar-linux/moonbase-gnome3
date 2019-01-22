OPTS+=" -D gudev=true -D goa=false -D google=false"

if ! ( module_installed systemd ); then
  OPTS+=" -D systemduserunitdir=\'no\' \
          -D tmpfilesdir=\'no\'
          -D logind=false"
fi

default_meson_build
