## 1. 机器人端 执行 slam 的 launch 文件

roslaunch robot_navigation robot_slam_laser.launch

## 2. PC 端 执行 rviz 图形化监控程序（载入 rviz 配置文件）

roslaunch robot_navigation slam_rviz.launch

## 3.启动一个键盘控制程序

rosrun teleop_twist_keyboard teleop_twist_keyboard.py

（建议将遥控速度调低以改善建图效果，建议速度不大于 0.25m/s 注意）

## 4.控制运动构建闭合地图，不要有碰撞



## 5.保存地图

### 命令：

roscd robot_navigation/maps

rosrun map_server map_saver -f map

### 结果：

保存完成后 maps 文件夹下就会有 map.pgm 和 map.yaml 两个文件



经测试：

speed 0.307252793988	turn 0.495171324334 

建图效果较佳