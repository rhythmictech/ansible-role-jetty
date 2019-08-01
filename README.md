# Ansible Role: Jetty
Ansible Role for Jetty 

## Requirements
- https://github.com/geerlingguy/ansible-role-java

## Role Variables 
There are three defaults that can be altered:
- `jetty_version: 9.4.9.v20180320`
    - the jetty version - currently this is the only version supported
    - the distribution file is pulled from `files`
- `jetty_base_dir: /opt`
    - where to unzip the jetty distribution
- `jetty_home: /opt/jetty`
    - symlink to become `JETTY_HOME`

## Dependencies 
- geerlingguy.java

## Example Playbook 

```
- hosts: jetty_servers
  roles:
    - role: github.com/rhythmictech/ansible-role-jetty
      become: yes
```

## License 
MIT 

## Author Information
- https://www.rhythmictech.com
- https://github.com/sblack4
