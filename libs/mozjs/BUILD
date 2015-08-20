cd $SOURCE_DIRECTORY/js/src &&

rm -rf editline ctypes/libffi &&

OPTS+=" --with-system-nspr  \
        --enable-threadsafe \
        --enable-readline   \
        --enable-system-ffi \
        --disable-static"  &&

unset CPPFLAGS &&
CXXFLAGS+=" -fpermissive" &&

default_config &&

sedit "s;mozjs-;mozjs-${VERSION::2};" Makefile &&

default_make

#for backwards compatibility
ln -sf /usr/bin/js /usr/bin/js17
