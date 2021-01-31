# Linux共享文件夹

//共享目录不见了，一般可能是虚拟机自带的工具 VMWare tools可能有问题；
//VMWare-tools是VMware虚拟机自带的一系列的增强工具，文件共享功能就是WMWare-tools工具里边的

## 若置灰，重新挂载Linux.iso，重新安装，进行下面步骤

### a) 虚拟机->重新安装VMware tools

### b)	 sudo mkdir /mnt/cdrom

### c) 	sudo mount /dev/cdrom /mnt/cdrom

### d)	 cd /mnt/cdrom

### e)	 sudo cp WMwareTool....tar.gz  ../

### f) 	cd ..

### g)	sudo tar -zxvf VMwareToo......tar.gz

### h)	cd wmware-tools-distrib

### j)	sudo ./vmware-install.pl

​		一路回车。