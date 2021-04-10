OPTS+=" -Dwin32-backend=false" \
OPTS+=" -Dvulkan=disabled -Ddemos=true -Dbuild-examples=false -Dbuild-tests=false -Dinstall-tests=false"

if [[ "$FFMPEG" == "y" ]]; then
  if [[ "$GSTREAMER" == "y" ]]; then
    MEDIA_BACKENDS="gstreamer,ffmpeg"
  fi
  MEDIA_BACKENDS="ffmpeg"
else
  if [[ "$GSTREAMER" == "y" ]]; then
    MEDIA_BACKENDS="gstreamer"
  else
    MEDIA_BACKENDS="none"
  fi
fi

OPTS+=" -Dmedia=$MEDIA_BACKENDS"

if in_depends $MODULE colord; then
   OPTS+=" -D colord=enabled"
fi

default_meson_build
