# FAQ

#### 本部署方案采用的那种安装方式安装HAProxy？

yum/apt 安装方式

#### 是否可以通过命令行修改HAProxy后台密码？

可以，修改配置文件`/etc/haproxy/haproxy.cfg`

#### 如果没有域名是否可以部署 HAProxy？

可以

#### 是否有可视化的管理工具？

默认开启 HAProxy Statistics Report 可视化界面，访问：*http://Internet IP:1080/haproxy* 即可

#### 如何修改上传的文件权限?

```shell
# 拥有者
chown -R haproxy.haproxy /data/wwwroot/
# 读写执行权限
find /data/wwwroot/ -type d -exec chmod 750 {} \;
find /data/wwwroot/ -type f -exec chmod 640 {} \;
```

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器