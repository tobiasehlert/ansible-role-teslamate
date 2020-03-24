# Ansible Role: TeslaMate
[![Build Status](https://api.travis-ci.com/tobiasehlert/ansible-role-teslamate.svg?branch=master)](https://travis-ci.com/github/tobiasehlert/ansible-role-teslamate)

Ansible Role for TeslaMate inside Docker on RHEL/CentOS.

## Requirements
This role requires an existing running docker environment to be ready to be used.

## Role Variables
to be added..

## Dependencies
This role does only setup the parts that are required for TeslaMate inside Docker.

Docker itself and an webserver in front of that is still something, that you need to install for yourself as well.

Ansible role to install:
* docker: [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker)
* nginx: [nginxinc.nginx](https://galaxy.ansible.com/nginxinc/nginx1) (config can be a little tricky)

## Example Playbook
```
- hosts: all
  roles:
    - tobiasehlert.teslamate
```

## License
MIT

## Author Information
This role was created in 2020 by [Tobias Lindberg](https://github.com/tobiasehlert).
