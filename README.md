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
- [geerlingguy.java](https://github.com/geerlingguy/ansible-role-java)

## Example Playbook 

```
- hosts: jetty_servers
  roles:
    - role: github.com/rhythmictech/ansible-role-jetty
      become: yes
```

## Development 
This role was development with [molecule](https://molecule.readthedocs.io/en/stable/getting-started.html)

To install all the development requirements
```
pip install ansible==2.8.1 \
            ansible-lint==4.1.0 \
            molecule==2.20.2 
```

To run the complete suite of tests (yamlint, ansible-lint, idempotency, etc) run `molecule test`

To test application of role on a docker image run `molecule converge`

To log into said image run `molecule login`

Destroy test container with `molecule destroy`

And if you're testing with packer (or anywhere else locally) you can use 
`ln -s $(pwd)/ansible-role-jetty rhythmic.jetty` so it will be available to the ansible provisioner

## License 
MIT 

## Author Information
- https://www.rhythmictech.com
- https://github.com/sblack4
