# Python3_MarchineLearning

## UBUNTU with Navida 1660ti 安装430.14显卡驱动
- a. 先关闭图形界面 
    + sudo systemctl set-default multi-user.target(还要关其他的)/sudo systemctl set-default graphical.target
    + sudo service lightdm stop/sudo service lightdm start
    + systemctl disable lightdm.service/ ln -s /lib/systemd/system/lightdm.service /etc/systemd/system/display-manager.service
- b. 必须重启进无图形化界面 sudo reboot， 不然装上驱动重启后，gdm3会与nvidiadriver冲突
- c. sh NVIDIA-Linux-x86_64-430.14.run 装上驱动，分布式无关，gcc无关
- d. install cuda with driver，best use runfile for selection installing nvidia driver or not
- e. 开启图形界面 sudo systemctl set-default graphical.target sudo reboot
- f. nvidia-smi
**Note**: 重装无数次，搞崩无数次得来的经验
- 万一装完黑屏，进入grub中recovery mode,等待进入命令行，sudo apt-get purge nvidia*,卸载驱动再重启
