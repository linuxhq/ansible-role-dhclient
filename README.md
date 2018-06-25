# ansible-role-dhclient

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-dhclient.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-dhclient)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-dhclient-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/dhclient)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Dynamic Host Configuration Protocol Client

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    dhclient: {}

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.dhclient
          dhclient:
            - interface: "{{ ansible_default_ipv4.address }}"
              settings:
                prepend:
                  domain-name-servers:
                    - 1.1.1.1
                    - 1.0.0.1
                request:
                  - broadcast-address
                  - domain-name
                  - domain-name-servers
                  - host-name
                  - routers
                  - subnet-mask
                require:
                  - domain-name-severs
                  - subnet-mask
                supersede:
                  host-name: dhcp.linuxhq.org
                  domain-name: linuxhq.org

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
