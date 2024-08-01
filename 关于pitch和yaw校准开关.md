关于pitch和yaw校准开关：
rm_manual/manual_base.cpp
找到gimbal/shooter_power_on_event_:
0 必不校准
1 则必校准
gimbal_output_on_判断是否有裁判系统（主控）？选择性校准
