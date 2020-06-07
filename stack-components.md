# 参数

## 组件及路径

haproxy部署包中不仅仅只有haproxy本身，还包含一序列支持haproxy运行所需的其他软件（这里称之为组件），下面列出主要组件名称、安装路径、配置文件地址等重要的信息：

### haproxy

haproxy安装目录: /var/lib/haproxy
haproxy配置文件：/etc/haproxy/haproxy.cfg
haproxy日志文件: /var/log/haproxy.log
## 端口号

下面是您在使用本镜像过程中，需要用到的端口号，请通过云控制台安全组进行设置

| 名称 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| HTTP | 80 | 通过http访问 | 必须 |
| HTTPS | 443 | 通过https访问 | 可选 |

## 版本号

组件对应的基本版本号可以通过云市场商品页面查看，但部署到您的服务器之后，版本会有一定的升级，故更为精准的版本请通过在服务器上运行命令查看：