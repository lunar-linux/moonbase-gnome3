(
  if [ "$ENABLE_GNOME" == "y" ] && ( ( ! in_depends libsoup GConf ) || ( ! in_depends libsoup libgnome-keyring ) ); then
    message "${PROBLEM_COLOR}gnome support requires libsoup to be build with gnome support."
    message "${PROBLEM_COLOR}Please rebuild libsoup and select gnome support."
    exit 1
  fi

  default_build

)> $C_FIFO 2>&1
