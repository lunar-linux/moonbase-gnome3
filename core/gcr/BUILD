OPTS+=" --disable-static \
        --disable-update-mime \
        --disable-schemas-compile"

default_build &&

# gcr wants to lock some memory to prevent swapping out private keys
install -Dm644 $SCRIPT_DIRECTORY/10-gcr.conf /etc/security/limits.d/10-gcr.conf
