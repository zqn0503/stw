#### 安装keepalived

- 下载源码包并安装

  ```sh
  wget http://www.keepalived.org/software/keepalived-2.0.7.tar.gz
  tar xvf keepalived-2.0.7.tar.gz
  cd keepalived-2.0.7
  ./configure --prefix=/usr/local/keepalived
  make && make install
  ```

- 完成以后会生成如下路径

  ```shell
  /usr/local/keepalived/etc/keepalived/keepalived.conf
  /usr/local/keepalived/etc/sysconfig/keepalived
  /usr/local/keepalived/sbin/keepalived
  ```

- 初始化及启动

  ```shell
  # keepalived启动脚本变量引用文件，默认文件路径是/etc/sysconfig/，也可以不做软链接，直接修改启动脚本中文件路径即可（安装目录下）
  cp /usr/local/keepalived/etc/sysconfig/keepalived  /etc/sysconfig/keepalived 
   
  # 将keepalived主程序加入到环境变量（安装目录下）
  cp /usr/local/keepalived/sbin/keepalived /usr/sbin/keepalived
   
  # keepalived启动脚本（源码目录下），放到/etc/init.d/目录下就可以使用service命令便捷调用
  cp /usr/local/src/keepalived-2.0.7/keepalived/etc/init.d/keepalived  /etc/init.d/keepalived
   
  # 将配置文件放到默认路径下
  mkdir /etc/keepalived
  cp /usr/local/keepalived/etc/keepalived/keepalived.conf /etc/keepalived/keepalived.conf
  
  # 加为系统服务：
  chkconfig –-add keepalived
  # 开机启动：
  chkconfig keepalived on
  # 查看开机启动的服务：
  chkconfig –-list
  # 启动、关闭、重启
  service keepalived start|stop|restart
  ```

  