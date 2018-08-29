OPTS+=" --enable-debug=no    \
        --enable-x11-backend \
        --enable-gdk-backend \
        --disable-egl-backend"

if module_installed libinput; then
  OPTS+=" --enable-evdev-input"
fi &&

default_build
