# Python3_MarchineLearning

装1660ti 430.14显卡驱动
- 先关闭图形界面 sudo systemctl set-default multi-user.target
- 必须重启进无图形化界面 sudo reboot， 不然装上驱动重启后，gdm3会与nvidiadriver冲突
- sh NVIDIA-Linux-x86_64-430.14.run 装上驱动，分布式无关，gcc无关
- 开启图形界面 sudo systemctl set-default graphical.target sudo reboot
- nvidia-smi
**Note**: 重装无数次，搞崩无数次得来的经验
