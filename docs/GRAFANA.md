# Grafana Setup

## Access

After starting the stack, open:

```txt
http://localhost:3000
```

Default lab credentials:

```txt
User: admin
Password: admin
```

## First steps

1. Open Grafana.
2. Change the default password when prompted.
3. Add data sources after the monitoring pipeline is ready.
4. Create dashboards for infrastructure health.

## Suggested dashboards

- EC2 CPU utilization
- Memory usage
- Disk usage
- Network traffic
- Availability status
- Alert summary

## Future integrations

Possible data sources:

- Zabbix plugin for Grafana
- Prometheus
- CloudWatch
- Loki

## Security notes

- Do not expose Grafana directly to the internet without authentication.
- Use strong passwords outside local labs.
- Restrict access by firewall or security group.
