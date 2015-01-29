This is an [Ansible](http://www.ansible.com/home) role for a
reasonably secure installation of [Grafana](http://grafana.org/).

Grafana can use several databases:

* ElasticSearch
* InfluxDb 
* OpenTSDB
* Graphite

This role only integrates with InfluxDB so far but changing that is
easy...

[nginx](http://nginx.org) is used to provide a reverse proxy.

You might also want to look at

* an Ansible role for [nginx](https://github.com/dhruvbansal/nginx-ansible-role)
* an Ansible role for [ElasticSearch](https://github.com/dhruvbansal/elasticsearch-ansible-role)

# What it Does

Creats a virtual host for nginx that serves the contents of a Grafana
release.

Also creates a logstash input file for nginx's logs.  Disable this by
setting `grafana_use_logstash` to `false`.

## Assumptions

* nginx is installed
* InfluxDB is installed
* Grafana has a appropriate user rights in InfluxDB

## Configuration & Logging

Creates the files:

* `/srv/grafana/shared` -- contains `config.js` and other shared files
* `/srv/grafana/current` -- link to current Grafana release
* `/var/log/grafana` -- log directory for nginx
* `/etc/logstash/conf.d/grafana.conf` -- inputs for logstash

## Services

Creates an `nginx` virtual host.

# Usage

Use the role in a playbook like this:

```yaml
- hosts: all
  roles:
    - grafana
```
