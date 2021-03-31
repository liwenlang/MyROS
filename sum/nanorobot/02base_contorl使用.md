## 1.编译工作空间

cd catkin_ws

catkin_make

## 2.设置为符号连接，标识为USB设备

cd /catkin_ws/src/base_control/script/

sudo ./inisetup.sh

## 3.设置环境变量

sudo ./setbase.sh 机器人名称

检查 echo $BASE_TYPE

## 4.机器人端设置master_ip

sudo vim /etc/hosts

修改master_ip 为树莓派ip

## 5.启动功能包

roslaunch base_control base_control.launch

## 6.键盘控制测试底盘运动

安装 sudo apt-get install ros-kinetic-teleop-twist-keyboard

rosrun teleop_twist_keyboard teleop_twist_keyboard.py

## 7.输出话题订阅查看

base_control 发布的话题主要有/battery 和/odom

rostopic echo /battery

rostopic echo /odom

订阅的话题 cmd_vel

rostopic echo /cmd_vel



