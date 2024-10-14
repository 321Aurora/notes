建立与dbus的映射：
执行下列命令，查看nuc的usb的物理地址：
ls /sys/class/tty/ttyUSB* -l
根据所查看的物理地址，修改rm.rules(路径为rm_bringup/scripts/udev),一般只需要修改KERNELS
随后运行下列脚本：
sh create_udev_rules.sh

利用minicom通信工具查看是否与串口建立通信：
usbDbus、usbReferee
使用方式：
sudo minicom -s
