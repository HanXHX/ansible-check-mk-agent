Role Name
=========

Install and configure check-mk-agent for Debian based systems.

Requirements
------------

- This role uses xinetd services. It doesn't manage systemd equivalent (or other inetd service). PR welcomed.
- Active support for Debian system. It should work on Ubuntu.

Role Variables
--------------

- `mk_port`: TCP port to listen
- `mk_only_from`: IP list who can call service. Default: empty list = all.
- `mk_xinetd_daemon`: default is xinetd, other systems will be managed later.
- `mk_disable`: disable inetd service

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      vars:
        mk_only_from:
          - mymonitoring.mydomain.tld
          - mymonitoring-slave.mydomain.tld
          - 127.0.0.1
      roles:
         - { role: HanXHX.check-mk-agent }

License
-------

GPLv2

Author Information
------------------

- Twitter: [@hanxhx_](https://twitter.com/hanxhx_)
