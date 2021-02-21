# 一.前置条件

## Ubuntu 和 ROS 版本对应

| ROS发布日期 | ROS版本              | 对应Ubutnu版本                                               |
| ----------- | -------------------- | ------------------------------------------------------------ |
| 2020.4      | ROS Noetic Ninjemys  | Ubuntu 20.04（Focal）                                        |
| 2018.4      | ROS Melodic Morenia  | Ubuntu 18.04 (Bionic) /Ubuntu 17.10 Artful                   |
| 2017.4      | ROS Lunar Loggerhead | Ubuntu 17.04 (Zesty) / Ubuntu 16.10 Yakkety, Ubuntu LTS 16.04 Xenial |
| 2016.3      | ROS Kinetic Kame     | Ubuntu 16.04 (Xenial) / Ubuntu 15.10 (Wily)                  |
| 2015.3      | ROS Jade Turtle      | Ubuntu 15.04 (Wily) / Ubuntu LTS 14.04 (Trusty)              |
| 2014.7      | ROS Indigo Igloo     | Ubuntu 14.04 (Trusty)                                        |
| 2013.9      | ROS Hydro Medusa     | Ubuntu 12.04 LTS (Precise)                                   |
| 2012.12     | ROS Groovy Galapagos | Ubuntu 12.04 (Precise)                                       |
| ...         | ...                  | ...                                                          |

## 软件更新：勾选前三，云代码选择阿里云镜像
#重要 
kinetic 勾选前四 选择中国服务器
选择清华的源，目前中科大的会报错
参考：http://www.autolabor.com.cn/book/ROSTutorials/chapter1/12-roskai-fa-gong-ju-an-zhuang/124-an-zhuang-ros.html


# 二.安装步骤

## 1 添加ROS软件源

  $ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
### 2 添加密钥

  $ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
### 3 安装ROS

  $ sudo apt update

```
问题：
错误:4 http://packages.ros.org/ros/ubuntu groovy Release                  
    404  Not Found [IP: 64.50.233.100 80]
解决：
实际上，每次update的过程就是在遍历/etc/apt/sources.list.d 下的所有list，只要删除相应报错的list文件，update将正常完成
```



$ sudo apt install ros-melodic-desktop-full

### 4 初始化rosdep

$ sudo rosdep init

```
问题：
rosdep: command not found
解决：
sudo apt install python-rosdep
```

```
问题：
ERROR: cannot download default sources list from: https://raw.githubusercontent.com/ros/rosdistro/master/rosdep/sources.list.d/20-default.list

解决：
\#打开hosts文件
sudo gedit /etc/hosts
\#在文件末尾添加
151.101.84.133 raw.githubusercontent.com
```

$ rosdep update

### 5 设置环境变量

  $ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
  $ source ~/.bashrc

### 6 安装rosinstall

  $ sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential
  安装
  
## 7.验证是否安装成功

roscore 

出现：

```
started roslaunch server http://ubuntu:40377/
ros_comm version 1.14.10


SUMMARY
========

PARAMETERS
 * /rosdistro: melodic
 * /rosversion: 1.14.10

```

# 三.使用roscore命令启动ROS Master



**1.启动ROS Master** 

$ roscore

**2.新终端-启动小海龟仿真器**

$ rosrun turtlesim turtlesim_node

**3.新终端-启动海龟控制节点**

$ rosrun turtlesim turtle_teleop_key
