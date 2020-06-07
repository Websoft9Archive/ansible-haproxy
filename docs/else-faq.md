# FAQ

#### What kind of installation method is used in this deployment solution to install HAProxy?

yum or apt

#### Can I reset password of HAProxy?

Yes, modify the configuration file `/etc/haproxy/haproxy.cfg`

#### If there is no domain name, can I deploy HAProxy?

Yes

#### Is there a web-base GUI database management tools?

Yes, HAProxy Statistics Report was enabled, you can visit it by URL: *http://Internet IP:1080/haproxy* 

#### How to change the permissions of filesytem?

Change owner(group) or permissions like below:

```shell
chown -R haproxy.haproxy /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a sequence of software in sequence in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference, just the terminology used by different manufacturers, actually cloud servers