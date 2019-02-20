OPTS+=" --enable-debug=no --enable-x11-backend --enable-gdk-backend"

if in_depends cogl wayland; then
  OPTS+=" --enable-egl-backend"
fi &&
if module_installed libinput; then
  OPTS+=" --enable-evdev-input"
fi &&

default_build
