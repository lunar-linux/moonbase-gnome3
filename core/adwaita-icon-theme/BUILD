default_build &&

if [ ! -e /etc/gtk-3.0/settings.ini ]; then
  cat > settings.ini <<EOF &&
[Settings]
gtk-fallback-icon-theme = gnome
EOF
  install -Dm0644 {,/etc/gtk-3.0/}settings.ini
fi
