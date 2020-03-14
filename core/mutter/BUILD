#remote desktop needs pipewire that is not yet included as a package
OPTS+=" -Dgles2=true \
        -Dprofiler=false \
        -Dnative_backend=true \
        -Dinstalled_tests=false"

if in_depends $MODULE wayland-protocols; then
  if ! in_depends $MODULE mesa-lib; then
    message "Wayland support in mutter requires mesa-lib"
    message "Compilation will continue with wayland disable"
    OPTS+=" -Dwayland=false -Dcore_tests=false"
  else
    OPTS+=" -Dwayland=true -Dopengl=true"
  fi
else
  if in_depends $MODULE mesa-lib; then
    OPTS+=" -Dopengl=true"
  fi
fi

default_meson_build
