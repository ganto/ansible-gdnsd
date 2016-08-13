## gdnsd

[gdnsd](http://gdnsd.org/) is a powerful Authoritative-only DNS server with
some advanced features such as geographic (or other sorts of) balancing,
redirection, wighting and service-state-conscious failover at the DNS layer.

The `ganto.gdnsd` Ansible role installs and configures the name service and
is able to generate zone files from name records defined in the Ansible
inventory.


### Installation

This role requires at least Ansible `v1.9.0`. To install it run:

```Shell
git clone https://github.com/ganto/ansible-gdnsd ganto.gdnsd
```


### Documentation

Currently the documentation is only available in raw format in the
[docs](/docs/) directory.


### Author

The content of this repository was written by:

- [Reto Gantenbein](https://linuxmonk.ch/) | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)

License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

