#### 1.安装tar命令(可选)
> - yum install -y tar

#### 2.下载源码包
> - wget http://nginx.org/download/nginx-1.12.2.tar.gz

#### 3.依赖
> - 1：需要gcc，系统自带了，没有的话，需要先安装 yum install gcc gcc-c++
> - 2：需要pcre，安装的命令： yum install pcre*
> - 3：需要zlib，安装的命令：yum install zlib zlib-devel
> - 4：如果需要支持ssl的话，安装OpenSSL，安装的命令：yum install openssl openssl-devel

#### 4.安装
> - (1)：./configure --prefix=/usr/local/nginx
> --with-http_stub_status_module --with-http_ssl_module
> > 如果提示确少啥，就加上相应的选项，比如缺少pcre的话，就加上
> > --with-pcre=/usr/common/temp/pcre-8.34 
> >
> > ps:正式网(./configure --prefix=/usr/local/nginx --with-http_stub_status_module --with-http_ssl_module --with-http_geoip_module --with-http_image_filter_module --with-http_perl_module --with-http_xslt_module --with-mail=dynamic --with-stream=dynamic --with-http_v2_module)
> >
> > [nginx安装问题汇总](http://blog.sina.com.cn/s/blog_6db6268c0102zc3m.html)
> - (2): 配置后就依次 make ， make install
> - (3): 安装路径为/usr/local/nginx

#### 5.配置服务并设置开机启动
> - 使用命令操作nginx
>
> >  /usr/local/nginx/sbin/nginx