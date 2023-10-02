OPTS+=" -Dwin32-backend=false" \
OPTS+=" -Dbuild-demos=true -Dbuild-examples=false -Dbuild-tests=false -Dbuild-demos=false"

if [[ "$FFMPEG" == "y" ]]; then
  if [[ "$GSTREAMER" == "y" ]]; then
    MEDIA_BACKENDS="gstreamer,ffmpeg"
  fi
  MEDIA_BACKENDS="-Dmedia-ffmpeg=enabled -Dmedia-gstreamer=enabled"
else
  if [[ "$GSTREAMER" == "y" ]]; then
    MEDIA_BACKENDS="-Dmedia-gstreamer=enabled -Dmedia-ffmpeg=disabled"
  else
    MEDIA_BACKENDS="-Dmedia-ffmpeg=disabled -Dmedia-gstreamer=disabled"
  fi
fi

if in_depends $MODULE colord; then
   OPTS+=" -D colord=enabled"
fi

default_meson_build
