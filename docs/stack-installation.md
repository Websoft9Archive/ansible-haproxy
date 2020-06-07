# Initial Installation

If you have completed the HAProxy deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:8161 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for HAProxy

## HAProxy Installation Wizard

1. Using local Chrome or Firefox to visit the URL *http://DNS:1080* or *http://Internet IP:1080*

2. Input username and password([Don't known password?](/stack-accounts.md#haproxy)), go to **HAProxy Statistics Report** console
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/haproxy/haproxy-statsgui-websoft9.png)

3. You can modify the password by modify the configuration of HAProxy */etc/haproxy/haproxy.cfg*  
   `stats auth admin:***** ` is username and password

   ```
   listen admin_stats 
    bind *:1080 
    mode http 
    maxconn 10 
    stats refresh 10s 
    stats uri /haproxy 
    stats realm Haproxy 
    stats auth admin:*****
    stats hide-version 
    stats admin if TRUE
   ```

> More useful HAProxy guide, please refer to [HAProxy Documentation](http://cbonte.github.io/haproxy-dconv/)

## Q&A

#### I can't visit the start page of HAProxy?

Your TCP:1080 of Security Group Rules is not allowed so there no response from Chrome or Firefox