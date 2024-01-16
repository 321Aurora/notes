测步兵发射：
1、先初始化can(看是can几则输入can几，bashrc中有已写好的初始化代码)
2、看左右摩擦轮和拨盘的id有无对上(clion中对对应的车型更改做临时应用，测完可改回)

（candump can1）可看can1所对应的所有设备(电机无响应可以由此判断是否连接成功)
3、roscore
4、mon launch rm_config rm_can_hw.launch
5、mon launch rm_config load_controllers.launch
6、rqt开joint_state controllers(开了才能看电机关节状态)
7、开trigger controllers(校准拨盘，校准结束后关闭)
8、开shooter controllers

若需调pid、卡弹、无反应则打开plotjuggler 看曲线情况 set_point(目标位置) process_value(过程位置)

可手动输入指令：rostopic pub /controllers/shooter_controller/command rm_msgs/ShootCmd "mode: 0
wheel_speed: 0.0
hz: 0.0
stamp:
  secs: 0
  nsecs: 0"
