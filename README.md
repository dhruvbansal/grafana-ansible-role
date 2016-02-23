This is an [Ansible](http://www.ansible.com/home) role for an
installation of [Grafana](http://grafana.org/).

Grafana can use several databases:

* ElasticSearch
* InfluxDb 
* OpenTSDB
* Graphite

* an Ansible role for [nginx](https://github.com/dhruvbansal/nginx-ansible-role)
* an Ansible role for [ElasticSearch](https://github.com/dhruvbansal/elasticsearch-ansible-role)
* an Ansible role for [InfluxDB](https://github.com/dhruvbansal/influxdb-ansible-role)

# What it Does

Installs Grafana service.

# Usage

Use the role in a playbook like this:

```yaml
- hosts: all
  roles:
    - grafana
```
