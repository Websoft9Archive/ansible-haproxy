# 初始化安装

在云服务器上部署 HAProxy 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:1080** 端口是否开启
3. 若想用域名访问 HAProxy，请先到 **域名控制台** 完成一个域名解析

## HAProxy 安装向导

1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://域名:1080/haproxy* 或 *http://Internet IP:1080/haproxy*, 提示需要登录
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/haproxy/haproxy-login-websoft9.png)

2. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#haproxy)），成功登录到 Haproxy Statistics Report 后台  
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/haproxy/haproxy-statsgui-websoft9.png)

3. 如需修改登录密码，请编辑HAProxy配置文件 */etc/haproxy/haproxy.cfg* 相关字段
   ```
   listen admin_stats 
    bind *:1080 
    mode http 
    maxconn 10 
    stats refresh 10s 
    stats uri /haproxy 
    stats realm Haproxy 
    stats auth admin:admin 
    stats hide-version 
    stats admin if TRUE
   ```

> 需要了解更多 HAProxy 的使用，请参考官方文档：[HAProxy Documentation](http://cbonte.github.io/haproxy-dconv/)

## 常见问题

#### 浏览器打开IP地址，无法访问 HAProxy（白屏没有结果）？

您的服务器对应的安全组1080端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### HAProxy 服务启动失败？

暂无