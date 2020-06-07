# Troubleshooting

We collect the most common troubleshooting of using HAProxy for your reference:

> Instance troubleshooting is closely related to the Instance provider that is Cloud Platform, refer to [Cloud Platform Documentation](https://support.websoft9.com/docs/faq/tech-instance.html)

#### How can I use the logs?

You can find the keywords **Failed** or **error** from the logs directory: `/var/logs/haproxy.log`

#### HAProxy service can't start?

Insufficient disk space, insufficient memory, and configuration file errors can make service could not be started. It is recommended to first check through the commands.

```shell
# restart mongodb service
systemctl status haproxy
journalctl  -u haproxy

# view disk space
df -lh

# view memory rate
free -lh
```