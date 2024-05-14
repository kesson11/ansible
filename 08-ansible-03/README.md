# Домашнее задание к занятию 3 
Oписание playbook:

## Clickhouse+Vector+Lighthouse Ansible-playbook

Clickhouse & vector & lighthouse setup

## Versions

* Clickhouse version: 22.3.3.44
* Vector version: 0.36.0
* Lighthouse version: actual from github


## Infrastructure requrements
* 3 hosts (Centos 7 VM's), details in inventory/prod.yml

## Playbook tasks:
1'st host:
* Download Clickhouse RPM-packages (clickhouse-client, clickhouse-server, clickhouse-common-static)
* Install downloaded Clickhouse packages
* Start Clickhouse service
* Create database for logs

2'nd host:
* Download and install Vector RPM via YUM package menager
* Configuring vector service from template (templates/vector.j2)

3'rd host:
* Install nginx & git via YUM package menager
* Clone Lighthouse git repository
* Configure nginx & lighthouse site

## INSTALL

```
ansible-playbook -i inventory/prod.yml site.yml
```

## TAGS

no tags in this release