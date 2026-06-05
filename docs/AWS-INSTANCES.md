# AWS Instances Monitoring

## Goal

This document describes the planned approach for monitoring AWS EC2 study instances with Zabbix and Grafana.

## Recommended metrics

- Instance availability
- CPU utilization
- Memory usage
- Disk usage
- Network traffic
- Service health

## Basic EC2 preparation

1. Launch a small EC2 instance for study.
2. Configure a restrictive security group.
3. Install Zabbix Agent on the instance.
4. Allow agent traffic only from the monitoring environment when possible.
5. Register the EC2 host in Zabbix.
6. Validate data collection.

## Security group guidance

For study environments, avoid exposing monitoring ports broadly.

Recommended approach:

- SSH only from your IP.
- Zabbix Agent access only from the monitoring host.
- No public exposure for Zabbix or Grafana without authentication and HTTPS.

## Documentation checklist

For each monitored instance, document:

- Instance name
- Region
- Operating system
- Monitoring method
- Templates applied
- Main metrics
- Alert rules
