Examples
--------

#### Configure Grafana Agent metrics scraping

```YAML
grafana_agent_metrics_config:
  global:
    scrape_interval: 1m
    remote_write:
    - url: http://1.2.3.4:1234/api/v1/push

grafana_agent_integrations_config:
  agent:
    enabled: true
  node_exporter:
    enabled: true
    disable_collectors:
    - mdadm
```
