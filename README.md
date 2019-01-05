# Ansible Role to install Gitea

**This role is based on [ansible-role-gogs] by [Jeff Geerling], author of [Ansible for DevOps].**

[![Build Status][travis-build-status]][travis-tests] [![Ansible Role][ansible-role-shield]][ansible-role]

Installs [Gitea], a Go-based front-end to Git, on RedHat or Debian-based linux systems.

After the playbook is finished, visit the Gitea server (on port 3000 by default), and you will be redirected to the /install page, where you can configure an administrator account and other default options.

## Requirements

Requires git (via `geerlingguy.git`) and at least the Gitea HTTP port (3000 by default) open on your system's firewall.

## Role Variables

See the [`defaults/main.yml`][defaults] file for more details.

    gitea_user: git
    gitea_user_home: /home/git

The user and home under which Gitea will run and be installed.

    gitea_binary_url: https://github.com/go-gitea/gitea/releases/download/v1.6.3/gitea-1.6.3-linux-amd64

Download URL for the Gitea binary.

    gitea_binary_checksum: fb46981b16b8dbc01ae0a87c02f4c1ef0ec7037beaa918e5bb4d9a278cf9b9c8

SHA256 checksum to verify the downloaded binary.

    gitea_http_port: 3000

HTTP port over which Gitea will be accessed.

## Dependencies

  - geerlingguy.git

## Example Playbook

    - hosts: server
      vars:
        gitea_http_port: 8080
      roles:
        - noplanman.gitea

## Tests

Docker is used to test the role with different operating systems.

## License

MIT

[Gitea]: https://github.com/go-gitea/gitea/ "Gitea on GitHub"
[ansible-role-gogs]: https://github.com/geerlingguy/ansible-role-gogs "Ansible Role Gogs on GitHub"
[Jeff Geerling]: https://www.jeffgeerling.com/
[Ansible for DevOps]: https://www.ansiblefordevops.com/
[travis-build-status]: https://img.shields.io/travis/noplanman/ansible-role-gitea.svg?style=flat-square "Travis-CI Build Status"
[travis-tests]: https://travis-ci.org/noplanman/ansible-role-gitea "Travis-CI Tests"
[ansible-role-shield]: https://img.shields.io/ansible/role/20665.svg?style=flat-square "Gitea on Ansible Galaxy"
[ansible-role]: https://galaxy.ansible.com/noplanman/gitea "Gitea on Ansible Galaxy"
