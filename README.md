Role Name
=========

Sets up a proxy using systemd-socket-proxyd.

Requirements
------------

None.

Role Variables
--------------

Proxy service parameters are specified by the following variables:

    UnitName: proxy_for_something       # Used as the name for systemd units (REQUIRED)
    ListenStream: localhost:1818        # Proxy listens on this address and port (REQUIRED)
    ProxyDestination: localhost:8080    # Traffic is forwarded to this address and port (REQUIRED)
    Description: Some proxy             # Used as a description in the unit files
    Documentation: Link to docs         # Used in systemd unit files

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: kedrosas
           vars:
                UnitName: very_special_proxy_for_ansible_galaxy
                ListenStream: 127.0.0.1:443
                ProxyDestination: galaxy.ansible.com:443
                Description: Such a pretty proxy
                Documentation: Red textbook on the right shelf

License
-------

BSD 3-clause

Author Information
------------------

Juraj Hrubša
Kedros, a.s.
https://www.kedros.sk/
