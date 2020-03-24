  # Ansible Role: TeslaMate
  [![Build Status](https://api.travis-ci.com/tobiasehlert/ansible-role-teslamate.svg?branch=master)](https://travis-ci.com/github/tobiasehlert/ansible-role-teslamate)

  Ansible Role for TeslaMate inside Docker on RHEL/CentOS.

  ## Requirements
  This role requires an existing running docker environment to be ready to be used.

  ## Role Variables
  Available variables are listed below, that need to be set for a setup to be completed. All default values can be found in `defaults/main.yml`.

  Define the domain names that you want to use, to access both web services.

      fqdn_teslamate: ""
      fqdn_grafana: ""

  Set the admin username and admin password for your Grafana installation.

      grafana_admin_username: ""
      grafana_admin_password: ""

  Generated credentials that are used for communications between applications and the database. Use a good randomized password!

      postgresql_database_username: ""
      postgresql_database_password: ""

  Specify your local timezone, if you don't want to use Stockholm. Work out your timezone name using the [TZ database name](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) in the linked Wikipedia page.

      teslamate_timezone: "Europe/Stockholm"

  ## Dependencies
  This role does only setup the parts that are required for TeslaMate inside Docker.

  Docker itself and an webserver in front of that is still something, that you need to install for yourself as well.

  Ansible role to install:
  * docker: [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker)
  * nginx: [nginxinc.nginx](https://galaxy.ansible.com/nginxinc/nginx1) (config can be a little tricky)

  ## Example Playbook
  ```
  - name: teslamate.yml
    hosts: all
    vars:
      - fqdn_teslamate: "teslamate.example.com"
      - fqdn_grafana: "grafana.example.com"
      - grafana_admin_username: "putsomefunnyadminusername"
      - grafana_admin_password: "asupersecretadminpassword"
      - postgresql_database_username: "somedatabaseusername"
      - postgresql_database_password: "asupersecretpassword"
    roles:
      - tobiasehlert.teslamate
  ```

  ## License
  MIT

  ## Author Information
  This role was created in 2020 by [Tobias Lindberg](https://github.com/tobiasehlert).
