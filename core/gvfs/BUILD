OPTS+=" --disable-static" &&

if ! ( module_installed systemd ); then
  OPTS+=" --disable-libsystemd-login"
fi

default_build
