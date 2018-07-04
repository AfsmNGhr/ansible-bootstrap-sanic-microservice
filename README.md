# Ansible Role for bootstraping sanic microservice

Steps:

- Create private repository on the bitbucket
- First commit README (need for git submodule)
- Create submodule in core repository
- Initialize submodule
- Copy bootstrap files
- Initial commit
- Push to repository

Example Playbook:

```yml
---

- name: Bootstrapping microservice
  hosts: localhost
  gather_facts: no
  roles:
    - bootstrap-sanic-microservice
  vars:
    bitbucket_user: *****
    bitbucket_password: *****
    team: test # our team
    repo: test.service # with dot service postfix
    registry: example.com # our docker registry
    core_path: /home/test/core.services # absolute path with services
    submodules_path: 'services/{{ repo }}'
    project_path:' /home/test/core.services/services/{{ repo }}' # absolute project path
```
