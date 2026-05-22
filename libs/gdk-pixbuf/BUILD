git cherry-pick -n 62b8f9fd0bb3b862823cd34afce4b389fbd27569 &&
#rm -f /usr/lib/gdk-pixbuf-2.0/2.10.0/loaders.cache &&

# others=enabled is for the xpm loader and few others, needed by gkrellm
OPTS+=" -Dothers=enabled  \
        -Dinstalled_tests=false \
        -Dgtk_doc=false \
        -Dintrospection=enabled \
        -Ddocumentation=false
        -Dtests=false \
        -Dlegacy_xpm=enabled"

default_meson_build
