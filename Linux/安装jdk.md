#### 1.安装tar或unzip命令(可选)
> - yum install -y tar 或  yum install unzip

#### 上传JDK8安装包到服务器解压
> - 注意,JC1.6安装包可能会没有执行权限 chmod 731 /usr/local/java/jdk1.6.0_32/bin/*进行赋权
#### 配置环境变量
> - vim /etc/profile 
> - 文件末尾添加以下内容：
>
> ```shell
> export JAVA_HOME=/usr/local/jdk-8
> export JRE_HOME=${JAVA_HOME}/jre
> export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib:$CLASSPATH
> export JAVA_PATH=${JAVA_HOME}/bin:${JRE_HOME}/bin
> export PATH=$PATH:${JAVA_PATH}
> ```

>
> - source /etc/profile使配置文件立即生效