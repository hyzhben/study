# Nginx

- 高效可靠
- 开源的

## 学习前准备

- CentOS7.2

1. 确认网络

   ```
   ping www.baidu.com
   ```

2. 确认yum可用

   ```
   yum list|grep gcc
   ```

3. 确认关闭iptables规则

   查看

   ```
   iptables -L
   ```

   ```
   iptables -t nat -L
   ```

   如果有，则需要关闭规则

   ```
   iptables -F
   ```

   ```
   iptables -t nat -F
   ```

4. 确认停用selinux

   查看，显示Disabled则表示已停用

   ```
   gentenforce
   ```

   否则，关闭它

   ```
   setenforce 0
   ```

5. 安装依赖

   ```
   yum -y install gcc gcc-c++ autoconf pcre pcre-devel make automake
   ```

6. 安装一些要用得到的包

   ```
   yum -y install wget httpd-tools vim
   ```

7. 进入opt目录，创建app、backup、download、logs、work文件夹，为了一致

   ```
   cd /opt/
   ```

   创建目录

   ```
   mkdir app
   ```

## Nginx简述

​	Nginx是一个开源且高性能、可靠的HTTP、代理服务

## 常见的HTTP服务

​	HTTPD-Apache基金会

​	IIS-微软

​	GWS-Google

# Nginx的优点

## 1. IO多路复用epoll

- 什么是IO多路复用

  ​	多个描述符的I/O操作都能在一个线程内并发交替地顺利完成，这就叫I/O多路复用，这里的“复用”指的是复用同一个线程。

- 什么是epoll

  IO多路复用的实现方式select、poll、epoll

  - 什么是select

    缺点：

    1. 能够监视问价描述符的数量存在最大限制
    2. 线性扫描效率低下

  - poll模型

  - 什么是epoll

    1. 每当FD就绪，采用系统的回调函数之间价格fd放入，效率更高。
    2. 最大连接无限制

## 2. 轻量级

- 功能模块少
- 代码模块化

## 3. CPU亲和（affinity）

- 为什么需要CPU亲和

- 什么是CPU亲和

  ​	是一种把Cpu核心和Nginx工作进程绑定方式，把每一个worker进程固定在一个cpu上执行，减少切换cou的cache miss，获得更好的性能。

## 4. sendfile

# Nginx快速安装

## Nginx快速搭建与基本参数使用

​	Mainline version - 开发版

​	Stable version - 稳定版

​	Legacy version - 历史版本

1. 打开官网：<http://nginx.org/>

2. 选择download

   ![191017-23：52：47](.\image\191017-23：52：47.png)

3. Linux安装选择最下面

   ![191017-23：54：30](.\image\191017-23：54：30.png)

4. 选择系统，我的是CentOS

   ![191017-23：56：01](.\image\191017-23：56：01.png)



5. 复制代码，这个是稳定版，下面那个是开发版本

   ![191017-23：57：07](.\image\191017-23：57：07.png)

   ```
   [nginx-stable]
   name=nginx stable repo
   baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
   gpgcheck=1
   enabled=1
   gpgkey=https://nginx.org/keys/nginx_signing.key
   module_hotfixes=true
   ```


6. 新建一个文本，把内容复制进去

   ```
   vim /etc/yum.repos.d/nginx.repo
   ```

7. i 进入插入模式，shift+int粘贴，exit退出插入模式，进入命令模式，:wq保存并退出

8. 用yum查看nginx，1.16.1版本已经加进来了，不知道原来有没有

   ```
    yum list |grep nginx
   ```

   ![191018-00：11：38](.\image\191018-00：11：38.png)

9. 安装nginx，安装过程中输入两次y进行确认

   ```
   yum install nginx
   ```

10. 若安装成功，可查看Nginx版本

    ```
    nginx -v
    ```

    ![191018-00：16：08](.\image\191018-00：16：08.png)



11. 查看编译的参数`nginx -V`（大写的V）

    ```
    nginx -V
    ```



## Nginx安装目录



yum安装的东西，可以使用以下命令查看安装了那些文件和目录

```
rpm -ql nginx
```

![191021-21：21：39](C:\Users\ben\Desktop\hyzh\study\nginx\image\191021-21：21：39.png)

**安装目录讲解**

| 路径                                        | 类型           | 作用                                       |
| ------------------------------------------- | -------------- | ------------------------------------------ |
| /etc/logrotate.d/nginx                      | 配置文件       | Nginx日志轮转，用于logrotate               |
| /etc/nginx                                  | 目录、配置文件 | Nginx主配置文件                            |
| /etc/nginx/nginx.conf                       |                |                                            |
| /etc/nginx/conf.d                           |                |                                            |
| /etc/nginx/conf.d/default.conf              |                |                                            |
| /etc/nginx/scgi_params                      | 配置文件       | cgi配置相关，fastcgi配置                   |
| /etc/nginx/uwsgi_params                     |                |                                            |
| /etc/nginx/fastcgi_params                   |                |                                            |
| /etc/nginx/koi-utf                          | 配置文件       | 编码转化映射转化文件                       |
| /etc/nginx/koi-win                          |                |                                            |
| /etc/nginx/win-utf                          |                |                                            |
| /etc/nginx/mime.types                       | 配置文件       | 设置http协议的Content-Type与扩展名对应关系 |
| /usr/lib/systemd/system/nginx-debug.service | 配置文件       | 用于配置出系统守护进程管理器方式           |
| /usr/lib/systemd/system/nginx.service       |                |                                            |
| /etc/sysconfig/nginx                        |                |                                            |
| /etc/sysconfig/nginx-debug                  |                |                                            |
| /usr/lib64/nginx/modules                    | 目录           | Nginx模块目录                              |
| /etc/nginx/modules                          |                |                                            |
| /usr/sbin/nginx                             | 命令           | Nginx服务的启动管理的终端命令              |
| /usr/sbin/nginx-debug                       |                |                                            |
| /usr/share/doc/nginx-1.16.1                 | 文件、目录     | Nginx的手册和帮助文件                      |
| /usr/share/doc/nginx-1.16.1/COPYRIGHT       |                |                                            |
| /usr/share/man/man8/nginx.8.gz              |                |                                            |
| /var/cache/nginx                            | 目录           | Nginx的缓存目录                            |
| /var/log/nginx                              | 目录           | Nginx的日志目录                            |

## Nginx编译配置参数

查看编译配置参数

```
nginx -V
```

![191021-21：44：23](C:\Users\ben\Desktop\hyzh\study\nginx\image\191021-21：44：23.png)

























