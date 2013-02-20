# build fixes for jpeg 9
sedit "27 i typedef int boolean;\n#define HAVE_BOOLEAN" src/af/util/xp/ut_jpeg.cpp &&

OPTS+=" --disable-static" &&

default_build
