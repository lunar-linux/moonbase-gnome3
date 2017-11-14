cd $SOURCE_DIRECTORY/js/src &&

rm -rf editline ctypes/libffi &&

OPTS+=" --with-system-nspr  \
        --with-system-icu   \
        --enable-threadsafe \
        --enable-readline   \
        --enable-system-ffi \
        --disable-static"  &&

unset CPPFLAGS &&
CXXFLAGS+=" -fpermissive" &&

default_build &&

#for backwards compatibility
ln -sf /usr/bin/js /usr/bin/js17
