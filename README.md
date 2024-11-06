# Jenkinsmaster Ansible Role

![Ansible Lint](https://github.com/mamrezb/jenkinsmaster-ansible-role/actions/workflows/lint.yml/badge.svg)
![Molecule Test](https://github.com/mamrezb/jenkinsmaster-ansible-role/actions/workflows/molecule.yml/badge.svg)
![Release Role](https://github.com/mamrezb/jenkinsmaster-ansible-role/actions/workflows/release.yml/badge.svg)


# Ansible Role: JenkinsMaster (Docker Compose)

An Ansible role that deploys Jenkins using Docker Compose on Linux servers.

## Requirements

- Ansible 2.9 or higher.
- Supported OS:
  - CentOS 7/8
  - RedHat 7/8
  - Ubuntu 18.04/20.04/22.04/24.04
- Docker and Docker Compose will be installed by this role.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
jenkins_docker_image: "jenkins/jenkins:lts"
jenkins_container_name: "jenkinsmaster"
jenkins_http_port: 8080
jenkins_volumes:
  - "/var/jenkins_home:/var/jenkins_home"

jenkins_plugin_list:
  - git
  - ldap
  - sonar
  - jira
  - github
  - bitbucket
  - gitlab

docker_compose_version: "v2.30.1"

# Optional: Custom Jenkins home directory
jenkins_home_dir: "/var/jenkins_home"
