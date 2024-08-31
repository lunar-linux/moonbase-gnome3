sed -e '/accounts_service\.py/s/dbusmock/dbusmock-tests/' \
    -e 's/assertEquals/assertEqual/'                      \
    -i tests/test-libaccountsservice.py &&

export LANG='en_US.UTF-8'

mv tests/dbusmock{,-tests} &&

#sed -e '/accounts_service\.py/s/dbusmock/dbusmock-tests/' \
 #   -e 's/assertEquals/assertEqual/'                      \
  #  -i tests/test-libaccountsservice.py &&

sed -i '/^SIMULATED_SYSTEM_LOCALE/s/en_IE.UTF-8/en_HK.iso88591/' tests/test-daemon.py &&

OPTS+=" -D docbook=false \
        -D gtk_doc=false \
        -D admin_group=wheel \
        -D introspection=true"

default_meson_build
