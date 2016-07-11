# ansible-role-dhclient

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-dhclient.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-dhclient)

RHEL/CentOS - Dynamic Host Configuration Protocol Client

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    dhclient_domain_name:
      - "{{ ansible_domain }}"
    dhclient_domain_name_servers: [ '8.8.8.8', '8.8.8.4' ]
    dhclient_interfaces: [ 'eth0' ]
    dhclient_request:
      - broadcast-address
      - domain-search
      - host-name
      - routers
      - subnet-mask
      - time-offset
    dhclient_require:
      - subnet-mask

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.dhclient

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
