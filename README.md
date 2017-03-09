:performing_arts: masquerade
============

A very simple Ansible role to enable iptables masquerading and IP forwarding on a host, to use it as a NAT Gateway for example.

Requirements
------------

Ansible 2.2

Role Variables
--------------

| Var                          |                        Default value |
|------------------------------|-------------------------------------:|
|masquerade_out_interface      | {{ ansible_default_ipv4.interface }} |
|masquerade_source             |                           0.0.0.0/0  |
|masquerade_dest               |                           0.0.0.0/0  |
|masquerade_protocol           |                                  all |

Example Playbook
----------------

    - hosts: ec2-gateway
      roles:
         - role: abelboldu.masquerade
           masquerade_out_interface: 'eth0'
           masquerade_source: '10.1.0.0/16'
           masquerade_protocol: 'tcp'


License
-------

BSD

Author Information
------------------

abel.boldu at gmx.com
