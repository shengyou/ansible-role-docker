# ansible-role-docker [![Build Status](https://travis-ci.org/shengyou/ansible-role-docker.svg?branch=master)](https://travis-ci.org/shengyou/ansible-role-docker)

=========

安裝 docker，修改自 [geerlingguy/ansible-role-docker](https://github.com/geerlingguy/ansible-role-docker)。

適用於
* Ubuntu 14.04
* Ubuntu 16.04
* CentOS 7

Requirements
------------

* ansible >= 2.4
* python >= 2.6

Role Variables
--------------

```
docker_edition: 'ce'
docker_package: "docker-{{ docker_edition }}"
docker_package_state: present

# Docker Compose options.
docker_install_compose: true
docker_compose_version: "1.23.0"
docker_compose_path: /usr/local/bin/docker-compose

# Used only for Debian/Ubuntu. Switch 'stable' to 'edge' if needed.
docker_apt_release_channel: stable
docker_apt_repository: "deb https://download.docker.com/linux/{{ ansible_distribution|lower }} {{ ansible_distribution_release }} {{ docker_apt_release_channel }}"

# Used only for RedHat/CentOS.
docker_yum_repo_url: https://download.docker.com/linux/centos/docker-{{ docker_edition }}.repo
docker_yum_repo_enable_edge: 0
docker_yum_repo_enable_test: 0
```


Dependencies
------------

none.

Example Playbook
----------------

```
- name: ansible-role-docker.yml
  hosts: your_host
  gather_facts: yes
  become: yes

  roles:
    - ansible-role-docker
```

License
-------

MIT
