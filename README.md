## Ansible Role: ganto.gdnsd

[![Travis CI](http://img.shields.io/travis/ganto/ansible-gdnsd.svg?branch=master&style=flat)](https://travis-ci.org/ganto/ansible-gdnsd) [![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-ganto.gdnsd-blue.svg?style=flat&logo=ansible)](https://galaxy.ansible.com/ganto/gdnsd)

[gdnsd](http://gdnsd.org/) is a powerful Authoritative-only DNS server with
some advanced features such as geographic (or other sorts of) balancing,
redirection, wighting and service-state-conscious failover at the DNS layer.

The [ganto.gdnsd](https://galaxy.ansible.com/ganto/gdnsd) Ansible role installs
and configures the domain name server and is able to generate and update DNS
zone files from name records defined in the Ansible inventory. It will also
properly increase the serial on zone updates.


### Installation

This role requires at least Ansible `v2.7.0`. To install it run:

```Shell
ansible-galaxy install ganto.gdnsd
```


### Documentation

Currently the documentation is only available in raw format in the
[docs](/docs/) directory.


### Author

The content of this repository was written by:

- [Reto Gantenbein](https://linuxmonk.ch/) | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)

License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)
