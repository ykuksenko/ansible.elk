# ELK

Ansible role to configure the complete open source Elastic stack (pre version 5). I try to make sure that all configuration options remain available without overcomplicating the role. This means you will probably want to override the default config files.

## Example Config

This is a an example single host to run all components. Note that two configs are pulled from a different role.

```
- hosts: elkhost
  sudo: yes
  roles:
    - role: elk
      elasticsearch_network_bind_host: "127.0.0.1"
      elasticsearch_network_publish_host: "127.0.0.1"
      elasticsearch_network_host: ''
      enable_elasticsearch: true
      enable_logstash: true
      enable_kibana: true
      enable_topbeat: true
      enable_filebeat: true
      enable_packetbeat: true
      enable_curator: true
      logstash_conf: roles/elkconf/templates/logstash.conf.j2
      curator_actions_conf: roles/elkconf/templates/curator_actions.yml.j2
```

## License

GPLv3

## Author Information

Yevgeniy Kuksenko
