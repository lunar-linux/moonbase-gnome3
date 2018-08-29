OPTS+=" --disable-static"

if ! ( module_installed systemd ); then
  OPTS+=" --disable-libsystemd-login"
fi
./autogen.sh &&

default_build
