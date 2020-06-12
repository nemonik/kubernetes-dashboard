# Kubernetes Web UI (Dashboard) role

![Basic role syntax check](https://github.com/nemonik/kubernetes-dashboard/workflows/Basic%20role%20syntax%20check/badge.svg)

An Ansible role for ensuring the configuration of the [Kubernetes Web UI (Dashboard)](https://metallb.universe.tf/).

## Requirements

Requires Kubernetes installed.

## Role Variables

| Variable                     | Required | Default               | Choices             | Comments                                         |
|------------------------------|----------|-----------------------|---------------------|--------------------------------------------------|
| kubernetes_dashboard_version | yes      | v2.0.0                | matches release tag | metallb version to install                       |
| images_cache_path            | no       | /vagrant/cache/images | Path                | Path to folder used to cache saved Docker images |

## Example Playbook

An example can be found used in my Hands-on DevOps course's [master-playbook.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/ansible/master-playbook.yml).

```
- hosts: masters
  remote_user: vagrant
  roles:
    - common
    - k3s-server
    - kubernetes-dashboard
```

The above Ansible playbook uses my [K3s-server role](https://github.com/nemonik/k3s-server-role) to install Lightweight Kubernetes (K3s).

For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>
