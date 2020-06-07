# Start or Stop the Services

These commands you must know when you using the HAProxy of Websoft9

## HAProxy

```shell
sudo systemctl start haproxy-server
sudo systemctl stop haproxy-server
sudo systemctl restart haproxy-server
sudo systemctl status haproxy-server

# you can use this debug mode if HAProxy service can't run
haproxy-server console
```

## HAProxy

```shell
sudo systemctl start haproxy-server
sudo systemctl stop haproxy-server
sudo systemctl restart haproxy-server
sudo systemctl status haproxy-server

# you can use this debug mode if HAProxy service can't run
haproxy-server console
```

### MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

### Redis

```shell
systemctl start redis
systemctl stop redis
systemctl restart redis
systemctl status redis
```