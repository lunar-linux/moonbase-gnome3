OPTS+="--with-x --with-mit-ext"

if module_installed systemd; then
  OPTS+=" --with-systemd"
fi

cp -f $SCRIPT_DIRECTORY/pam.d/gnome-screensaver data/ &&

default_build
