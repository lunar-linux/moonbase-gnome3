OPTS+=" --disable-static \
        --disable-update-mime \
        --disable-schemas-compile"

default_build &&

install -m0644 $SCRIPT_DIRECTORY/61-gnome-bluetooth-rfkill.rules /usr/lib/udev/rules.d/

# gcr wants to lock some memory to prevent swapping out private keys
install -Dm644 $SCRIPT_DIRECTORY/10-gcr.conf /etc/security/limits.d/10-gcr.conf
