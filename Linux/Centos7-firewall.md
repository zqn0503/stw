- **查看当前已经开放的端口：**

  ```shell
  firewall-cmd --list-ports
  ```

  

- **开启端口，以`8888`为例：**

  ```shell
  firewall-cmd --zone=public --add-port=8888/tcp --permanent
  ```

  

- **重启防火墙：**

  ```shell
  firewall-cmd --reload
  ```

  

- **其他指令：**

  ```shell
  # 关闭防火墙
  firewall systemctl stop firewalld.service
  
  # 关闭防火墙开机启动
  firewall sustemctl disable firewalld.service
  ```

  