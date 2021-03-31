# 01配置wifi连接

## 1.连接网线,配置网管

输入http://172.16.0.1:2011/ 账户密码：admin

查看MAC （B8-27-EB-AD-4C-3C）得到 (172.16.100.52 )分配的IP地址

## 2.远程连接SSH，修改wifi配置

```
sudo vim /etc/wpa_supplicant/wpa_supplicant.conf
```

修改 ssid 为你路由器的 ssid，psk 为 wifi 密码

## 3.修改完成后保存退出，重启树莓派

## 4.打开路由器管理界面，可以看到树莓派已经连接上 wifi 了

设备名应该为 nanorobot



## 5.无线网卡 MAC 地址和 IP 绑定

树莓派3B主板的无线网卡只支持2.4GHz 802.11.b/g/n频段的wifi信号， 

不支持5GHz 802.11.ac频段的wifi信号，可能导致无法识别出wifi热点。 

------



### 无法连接？ 尝试用手机发送热点，组建局域网

参看https://www.cnblogs.com/fireflys/p/10600190.html

手机热点不稳定，企业路由器网关管理严格，建议单独用一个路由器



#### 修改静态ip方法

sudo vim /etc/network/interfaces





