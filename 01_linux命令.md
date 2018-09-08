只学CentOS

sudo yum update
sudo yum install docker
RPM是Red-Hat Package Manager（RPM软件包管理器）


rpm -ivh jdk-8u51-linux-x64.rpm


#rpm -qa |grep java
# netstat –anp | grep 8080

cd
ls
pwd

传文件
# yum install  lrzsz -y
# rpm -qa |grep lrzsz
# rz

# find /etc -name '*srm*'　　#使用通配符*(0或者任意多个)。表示在/etc目录下查找文件名中含有字符串‘srm’的文件

安装软件：执行rpm -ivh rpm包名

1、获得软件包相关的信息用rpm -q，q表示查询query，后面可以跟其他选项，查询一个包是否被 安装 ：# rpm -q < rpm package name>
2、获得软件包的信息； q表示查询query，a 表示all，在所有包中执行查询列出所有被安装的rpm package ：# rpm -qa< rpm package name>


上传文件的执行命令：

#rz  

模块设计
1、角色设计
1、权限系统设计

这四个前后定义一定是这个顺序
#vim /etc/profile 
# i 为进入编辑模式
#esc是退出编辑然后进行命令模式 
#:wq 为退出加保存

# 重启命令

jdk-8u181-linux-x64.tar.gz

注册服务
# sudo ln -s /var/apps/xxxx.jar  /etc/init.d/test


 sudo ln -s /var/apps/p2gblock-0.0.1-SNAPSHOT.jar  /etc/init.d/aaa


# Ctrl+c
在命令行下起着终止当前执行程序的作用，


netstat –anp | grep 9090
netstat –anp | grep 20


# 打开端口号：iptables -A INPUT -ptcp --dport  端口号-j ACCEPT


iptables -A INPUT -ptcp --dport  9090-j ACCEPT


nc -lp 23 &(打开23端口，即telnet)

sudo ln -s /var/apps/p2gblock-0.0.1-SNAPSHOT.jar  /etc/init.d/ccc




    sudo chmod +x /etc/init.d/test

查看 joyupx 的进程：
    ps -aux | grep joyupx


    netstat -tunlp |grep 22


     service /etc/sysconfig/iptables restart


     iptables -A INPUT -p tcp --dport 9090 -j ACCEPT 

     firewall-cmd --state


     systemctl start test

#  vi filename :打开或新建文件，并将光标置于第一行首

systemctl reload test.service
rm 删除

systemctl daemon-reload


firewall-cmd --zone=public --add-port=9090/tcp --permanent

/etc/systemd/system/startTest.sh

java -jar /var/apps/p2gblock-0.0.1-SNAPSHOT.jar

/usr/java -jar /var/apps/p2gblock-0.0.1-SNAPSHOT.jar


 nohup java -jar /var/apps/p2gblock-0.0.1-SNAPSHOT.jar

 # systemctl list-unit-files|grep enabled


 sudo ln -s /var/apps/p2gblock-0.0.1-SNAPSHOT.jar  /etc/init.d/aaa

 /usr/java
 /etc/systemd/system


ExecStart=/etc/systemd/system/startTest.sh
ExecStop=/etc/systemd/system/stopTest.sh

/usr/java/jdk1.8.0_181/bin/java




systemctl restart firewalld.service.service



# firewall-cmd --zone=public --add-port=9090/tcp --permanent
# firewall-cmd --reload
# firewall-cmd --zone= public --query-port=9090/tcp

# systemctl restart test.service
# firewall-cmd --query-port=9090/tcp
# firewall-cmd --add-port=9090/tcp


telnet 116.62.244.230 9090
wget 116.62.244.230:9090
wget 172.16.62.90:9090



# systemctl start test.service
# systemctl status test.service -l
# firewall-cmd --add-port=80/tcp
# systemctl enable firewalld 开机启用 systemctl start firewalld 启动
# firewall-cmd --query-port=80/tcp
# wget 172.16.62.90:80 私网测试
# wget 116.62.244.230:80 公网测试
