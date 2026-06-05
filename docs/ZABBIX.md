# Zabbix Setup

## Access

After starting the stack, open:

```txt
http://localhost:8080
```

Default lab credentials:

```txt
User: Admin
Password: zabbix
```

## First steps

1. Open the Zabbix web interface.
2. Confirm that the Zabbix server is running.
3. Change the default password in real environments.
4. Add a host for a local machine or AWS study instance.
5. Link a Linux template when monitoring Linux servers.

## AWS instance monitoring plan

For an AWS EC2 study instance:

1. Install Zabbix Agent on the EC2 instance.
2. Allow traffic only from the monitoring host where possible.
3. Configure the instance host in Zabbix.
4. Link the correct OS template.
5. Validate metrics such as CPU, memory, disk and availability.

## Security notes

- Do not expose Zabbix directly to the internet.
- Use strong passwords outside local labs.
- Restrict security group inbound rules.
- Document monitored hosts and templates.
