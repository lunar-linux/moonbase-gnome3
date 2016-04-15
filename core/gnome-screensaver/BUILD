OPTS+="--with-x --with-mit-ext" &&

if module_installed systemd; then
  OPTS+="  --with-systemd"
fi &&

OPTS+=" --libexecdir=/usr/lib/$MODULE" &&

cp -f $SCRIPT_DIRECTORY/pam.d/gnome-screensaver data/ &&

default_build
