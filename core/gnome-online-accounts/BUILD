if ! in_depends $MODULE krb5; then
# Kerberos support is not set
#
# Heimdal install its krb-config file
# to /usr/bin which is in our PATH.
if module_installed heimdal; then
sedit 's:enable_kerberos=auto:enable_kerberos=no:' configure.ac
sedit 's|$PATH:/usr/kerberos/bin|/usr/kerberos/bin|' configure.ac
fi
fi

autoreconf -fi &&

OPTS+=" --disable-static      \
        --enable-exchange     \
        --enable-facebook     \
        --enable-flickr       \
        --enable-google       \
        --enable-imap-smtp    \
        --enable-owncloud     \
        --enable-windows-live \
        --enable-media-server" &&

default_build
