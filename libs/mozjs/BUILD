(

  cd $SOURCE_DIRECTORY/js/src &&

  OPTS+=" --with-system-nspr --enable-threadsafe" &&

  CXXFLAGS+=" -fpermissive" &&

  default_build &&

  #for backwards compatibility
  ln -sf /usr/lib/libmozjs${VERSION%\.*}.a /usr/lib/libjs_static.a &&

  ln -sf /usr/bin/js17 /usr/bin/js

) > $C_FIFO 2>&1
