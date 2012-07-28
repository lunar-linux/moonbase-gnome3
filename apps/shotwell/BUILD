(

  # 0.12.3 doesn't compile with current vala
  # see http://redmine.yorba.org/issues/5453
  sedit "s:store.remove(wrapper.get_iter()):Gtk.TreeIter iter = wrapper.get_iter();store.remove(ref iter):" src/sidebar/Tree.vala &&

  OPTS+=" --release --install-headers" &&

  default_build

) > $C_FIFO 2>&1
