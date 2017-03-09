:performing_arts: masquerade
============

A very simple Ansible role to enable iptables masquerading and IP forwarding on a host, to use it as a NAT Gateway for example.

Requirements
------------

Ansible 2.2

Role Variables
--------------

| Var                          |                     Default value |
|------------------------------|----------------------------------:|
|masquerade_outbound_interface |{{ ansible_default_ipv4.address }} |
|masquerade_inbound_interface  |                                 * |
|masquerade_source             |                        0.0.0.0/0  |
|masquerade_dest               |                        0.0.0.0/0  |
|masquerade_protocol           |                               all |

Dependencies
------------

IPTables


Example Playbook
----------------

    - hosts: ec2-gateway
      roles:
         - role: abelboldu.masquerade
           masquerade_source: '10.1.0.0/16'
           masquerade_protocol: 'tcp'


License
-------

BSD

Author Information
------------------

abel.boldu at gmx.com
