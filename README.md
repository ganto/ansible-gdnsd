## Ansible Role: ganto.gdnsd

[![CI](https://github.com/ganto/ansible-gdnsd/workflows/CI/badge.svg?event=push)](https://github.com/ganto/ansible-gdnsd/actions?query=workflow%3ACI)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-ganto.gdnsd-blue.svg?style=flat&logo=ansible)](https://galaxy.ansible.com/ganto/gdnsd)
[![Read the Docs](https://img.shields.io/badge/docs-ansible--gdnsd-darkblue.svg?style=flat&logo=read-the-docs)](https://ansible-gdnsd.readthedocs.io/)

[gdnsd](https://gdnsd.org/) is a powerful Authoritative-only DNS server with
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

The role documentation is available online at [ansible-gdnsd.readthedocs.io](https://ansible-gdnsd.readthedocs.io).

It can be built locally from the [docs](docs/) directory by running:
```Shell
cd docs && make html
```

### License

[GPL-3.0](https://spdx.org/licenses/GPL-3.0-or-later.html) or some later version


### Author

The content of this repository was written by:

- [Reto Gantenbein](https://linuxmonk.ch/) | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)
