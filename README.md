# Kubernetes Web UI (Dashboard) role

![Basic role syntax check](https://github.com/nemonik/kubernetes-dashboard/workflows/Basic%20role%20syntax%20check/badge.svg)

An Ansible role for ensuring the configuration of the [Kubernetes Web UI (Dashboard)](https://metallb.universe.tf/).

## Requirements

Requires Docker and Kubernetes installed.

## Role Variables

| Variable                     | Required | Default               | Choices             | Comments                                         |
|------------------------------|----------|-----------------------|---------------------|--------------------------------------------------|
| kubernetes_dashboard_version | yes      | v2.0.0                | matches release tag | Kubernetes Dashboard version to install          |
| images_cache_path            | no       | not defined           | Path                | Path to folder used to cache saved Docker images |
| cache_container_timeout      | no       | 300 seconds           | Integer value       | Number of seconds before Ansible times out       |

## Example Playbook

An example can be found used in my Hands-on DevOps course's [ansible/master-playbook.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/ansible/master-playbook.yml).

```
- hosts: masters
  remote_user: vagrant
  roles:
    - common
    - docker
    - k3s-server
    - kubernetes-dashboard
```


The above Ansible playbook uses my

- [Common role](https://github.com/nemonik/common-role) to configure the instance past the base CentOS 7, Alpine 3.10 or Ubuntu Bionic image
- [Docker role](https://github.com/nemonik/docker-role) to install and configure Docker
- [K3s-server role](https://github.com/nemonik/k3s-server-role) to install Lightweight Kubernetes (K3s)
- [metallb role](https://github.com/nemonik/metallb-role) to install MetalLB
- [This role](https://github.com/nemonik/kubernetes-dashboard-role) to install the Kubernetes Dashboard

For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>
