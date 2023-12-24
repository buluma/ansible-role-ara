# [Ansible role ara](#ara)

Install and configure ara on your system.

|GitHub|Version|Issues|Pull Requests|
|------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-ara/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-ara/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-ara.svg)](https://github.com/buluma/ansible-role-ara/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-ara.svg)](https://github.com/buluma/ansible-role-ara/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-ara.svg)](https://github.com/buluma/ansible-role-ara/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-ara/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.ara
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-ara/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.buildtools
    - role: buluma.epel
    - role: buluma.python_pip
    - role: buluma.service
    - role: buluma.systemd
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-ara/blob/master/defaults/main.yml):

```yaml
---
# defaults file for ara

# The ansible.cfg to modify.
ara_configuration_file: /etc/ansible/ansible.cfg

# The user to run ara as. Typically root, but if you run playbooks under your username, ara saves data in your homedirectory. In that case change the ara_user to your username.
ara_user: root

# This role tries to "find" python. If you are using a specific path to python,
# you can set `ara_callback_plugins`. For example:
# ara_python_plugins_path: /home/username/venv/site-packages/ara/plugins/callback

# Extra options can be set using this structure.
# ara_configuration:
#   - option: port
#     value: 9191
#   - option: host
#     value: "0.0.0.0"
#   - option: playbook_per_page
#     value: 10
#   - option: result_per_page
#     value: 25
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-ara/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.buildtools](https://galaxy.ansible.com/buluma/buildtools)|[![Ansible Molecule](https://github.com/buluma/ansible-role-buildtools/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-buildtools/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-buildtools.svg)](https://github.com/shadowwalker/ansible-role-buildtools)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-epel.svg)](https://github.com/shadowwalker/ansible-role-epel)|
|[buluma.python_pip](https://galaxy.ansible.com/buluma/python_pip)|[![Ansible Molecule](https://github.com/buluma/ansible-role-python_pip/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-python_pip/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-python_pip.svg)](https://github.com/shadowwalker/ansible-role-python_pip)|
|[buluma.service](https://galaxy.ansible.com/buluma/service)|[![Ansible Molecule](https://github.com/buluma/ansible-role-service/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-service/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-service.svg)](https://github.com/shadowwalker/ansible-role-service)|
|[buluma.systemd](https://galaxy.ansible.com/buluma/systemd)|[![Ansible Molecule](https://github.com/buluma/ansible-role-systemd/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-systemd/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-systemd.svg)](https://github.com/shadowwalker/ansible-role-systemd)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-ara/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|8|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|bionic|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-ara/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-ara/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-ara/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)


### [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
