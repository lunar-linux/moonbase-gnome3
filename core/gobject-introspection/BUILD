OPTS+=" -Dgtk_doc=false -Ddoctool=disabled"

default_meson_build &&

# These seem to have fallen out of the default install but they're needed
# by python-pygobject which is needed by an awful lot of things, so let's
# put them back
install -m 644 $SOURCE_DIRECTORY/$MODULE-$VERSION/gir/* /usr/share/gir-1.0
