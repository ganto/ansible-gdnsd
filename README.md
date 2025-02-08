## Ansible Role: ganto.gdnsd

[![CI](https://github.com/ganto/ansible-gdnsd/actions/workflows/ci.yml/badge.svg)](https://github.com/ganto/ansible-gdnsd/actions/workflows/ci.yml)
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

This role requires at least Ansible `v2.8.0`. To install it run:

```Shell
ansible-galaxy install ganto.gdnsd
```

### Documentation

The role documentation is available online at [ansible-gdnsd.readthedocs.io](https://ansible-gdnsd.readthedocs.io).

It can be built locally from the [docs](docs/) directory by running:

```Shell
cd docs && make html
```

### Development

#### Testing

There is a [Molecule](https://molecule.readthedocs.io/) test profile that can be used to verify the basic functionality of the role. The default scenario is using the [podman](https://podman.io/) container driver. If you prefer [docker](https://www.docker.com/) you can select the corresponding scenario with the `-s docker` molecule arguments.

1. Ensure you have the necessary dependencies installed (e.g. in a Python [venv](https://docs.python.org/3/tutorial/venv.html)):

```
pip install -r molecule/podman/requirements.txt         # for podman
# or
pip install -r molecule/docker/requirements.txt         # for docker
```

2. Run the test suite. The options in brackets are optional but useful if you need to troubleshoot issues:

```
molecule [-vvv] test [--destroy never][-s docker]
```

3. If you used `--destroy never` the container will remain after the test run and can be inspected interactively via:

```
podman exec -it <container-id> /bin/sh                  # for podman
# or
docker exec -it <container-id> /bin/sh                  # for docker
```

4. Once you're done with inspecting the instance it has to be deleted before a new test run can be started:

```
molecule destroy [-s docker]
```

### License

[GPL-3.0](https://spdx.org/licenses/GPL-3.0-or-later.html) or some later version

### Author

The content of this repository was written by:

- [Reto Gantenbein](https://linuxmonk.ch/) | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)
