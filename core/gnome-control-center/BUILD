if ! in_depends $MODULE samba; then
  #   printer applet is depended on samba
  #   be aware of all the weird guys that do not want to have samba installed
  sedit 's|extern GType cc_printers_panel_get_type|//extern GType cc_printers_panel_get_type|' shell/cc-panel-loader.c
  sedit 's|PANEL_TYPE("printers"|//PANEL_TYPE("printers"|' shell/cc-panel-loader.c
  sedit "/'printers'/d" panels/meson.build
  sedit "/subdir('printers')/d" tests/meson.build
fi &&

if ! in_depends $MODULE krb5; then
  #   user accounts applet is depended on krb5
  #   be aware of all the weird guys that do not want to have krb5 installed
  sedit 's|extern GType cc_user_panel_get_type|//extern GType cc_user_panel_get_type|' shell/cc-panel-loader.c
  sedit 's|PANEL_TYPE("user-accounts"|//PANEL_TYPE("user-accounts"|' shell/cc-panel-loader.c
  sedit "/'user-accounts'/d" panels/meson.build
fi &&

default_meson_build
