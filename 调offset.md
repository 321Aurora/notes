调offset

1.用有线连接接入交换机，进.bashrc文件里将ros URI注释解开(才能统一IP)

2.wired命令进行连接，用户名变成小电脑上的则说明连接成功，密码：dynamicx  

ssh-copy-id dynamicx@192.168.100.2不用每次打密码

3.如果碰到roscore有另外一个在运行则说明自启服务没关  关闭后再开roscore

4.mon launch rm_config rm_ecat_hw.launch（看是用的ecat还是can）

5.mon launch rm_config load_controllers.launch

6.rqt 发布指令  (joint_state controllers开了才能看电机关节状态) 

7.clion里将offset调成0，上传后重新跑程序校准，校准后拨盘此刻位置为0，再手动拨拨盘到单发限位看joint state -trigger-position的数值，记录为offset并上传，再跑程序校准，rqt里mode设为1启动摩擦轮，使offset生效。



附：

1.message publisher勾上说明在发  没有则没有发 

2.rosrun plotjuggler plotjuggler看曲线 (joint state -trigger-position看拨盘位置)『set_point(目标位置) process_value(过程位置)是调pid的』

