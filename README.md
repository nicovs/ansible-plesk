ansible-plesk
=============

This role install Odin Plesk panel and runs the initial configuration script
along with some predefined variables. The role performs a typical installation
of Plesk components. To perform installation of Plesk with additional
components, check the `install_components` variable below.

Role Variables
--------------
The most common variable that you would use is `plesk.release_id`, which
configures what version of Plesk should be installed. Currently, it defaults to
`PLESK_18_0_40` that will install Plesk 12.0.18. You can use `plesk.license` to
specify a valid Plesk license key and install it.

Variables for initial configuration of Plesk are also specified. In particular
the following variables are specified in `defaults/main.yml`

    admin_password: changeme
    email: test@mycompany.com
    hostname: server.myserver.com
    company: My Company
    name: Hosting Services
    phone: +1234567890
    address: Address Str. 1
    city: My City
    state: My State
    zip: 12345
    country: GR
    release_id: PLESK_18_0_40
    license: ""
    install_components: [ ]

Change `admin_password` to something more secure. `install_components` is a list
of Plesk components that should be installed. By default, this list is empty,
and the installation is performed using typical components

Example Playbook
----------------
To use this playbook, create a playbook with the following:

    - hosts: servers
      remote_user: root
      roles:
        - plesk

<!-- vi: tw=80 -->
