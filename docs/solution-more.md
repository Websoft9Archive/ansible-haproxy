# More

Each of the following solutions has been proven to be effective and we hope to be helpful to you.

## Enable HAProxy Statistics Report

The HAProxy Statistics Report was enabled by default, just visit the URL:*http://Internet IP:1080/haproxy*

## Enable HAProxy log

Log was enabled by default, check the file `/etc/rsyslog.conf` to get the configuration details

## High availability

You should deploy the software **Keepalived** to implement the High availability for HAProxy

## HAProxy Cluster configuration

Simply add the information of the cluster server to be managed in the configuration file to enable the HAProxy cluster. Examples are as follows:

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