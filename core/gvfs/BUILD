OPTS+=" --disable-static" &&

OPTS+=" --libexecdir=/usr/lib/$MODULE" &&

if ! ( module_installed systemd ); then
  OPTS+=" --disable-systemd"
fi

default_build
