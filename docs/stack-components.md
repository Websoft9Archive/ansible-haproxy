# Parameters

The HAProxy deployment package contains a sequence software (referred to as "components") required for HAProxy to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

### HAProxy

HAProxy configuration file: */etc/haproxy/haproxy.cfg*  
HAProxy logs directory: */var/log/haproxy.log*  

### Other

No other components

## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

You can run the cmd `netstat -tunlp` to list all used ports, and we list the following most useful ports for you:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| TCP | 1080 | HTTP requests for HAProxy  Statistics Report | Optional |
| TCP | 5000 | for  HAProxy  | Optional |


## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# HAProxy version
haproxy -v
```
