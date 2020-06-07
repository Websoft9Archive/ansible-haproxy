# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 开启监控

使用[Websoft9](https://www.websoft9.com)提供的HAProxy部署方案，默认已经设置HAProxy Statistics Report，只需直接访问即可：*http://服务器公网IP:1080/haproxy*

## 开启HAProxy日志

默认已经开启，查看 `/etc/rsyslog.conf` 配置文件了解详情

## 高可用性

通过部署 Keepalived 实现 HAProxy的高可用性

## 集群配置

只需在配置文件中添加需要管理的集群服务器信息即可启用HAProxy集群，范例如下：

```
# [HTTP Site Configuration]
listen  http_web 192.168.10.10:80
        mode http
        balance roundrobin  # Load Balancing algorithm
        option httpchk
        option forwardfor
        server server1 192.168.10.100:80 weight 1 maxconn 512 check
        server server2 192.168.10.101:80 weight 1 maxconn 512 check

# [HTTPS Site Configuration]
listen  https_web 192.168.10.10:443
        mode tcp
        balance source# Load Balancing algorithm
        reqadd X-Forwarded-Proto: http
        server server1 192.168.10.100:443 weight 1 maxconn 512 check
        server server2 192.168.10.101:443 weight 1 maxconn 512 check
```