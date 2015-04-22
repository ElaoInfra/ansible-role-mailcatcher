<img src="http://www.elao.com/images/corpo/logo_red_small.png"/>

# Ansible Role: mailcatcher

This role will assume the setup of mailcatcher

It's part of the ELAO [Ansible stack](http://ansible.elao.com) but can be used as a stand alone component.

## Requirements

- Ansible 1.7.2+

## Dependencies

None.

## Installation

Using ansible galaxy:

```bash
ansible-galaxy install elao.mailcatcher
```
You can add this role as a dependency for other roles by adding the role to the meta/main.yml file of your own role:

```yaml
dependencies:
  - { role: elao.mailcatcher }
```

## Role Handlers

| Name                  | Type    | Description         |
| --------------------- | ------- | ------------------- |
| `mailcatcher restart` | Service | Restart mailcatcher |

## Role Variables

| Name                                 | Default           | Type   | Description                   |
| ------------------------------------ | ----------------- | ------ | ----------------------------- |
| `elao_mailcatcher_config_template`   | config/default.j2 | String | Main config template          |
| `elao_mailcatcher_config['http-ip']` | 0.0.0.0           | String | IP address of the http server |

### Configuration example

```yaml
elao_mailcatcher_config:
  'http-ip':    0.0.0.0
  'http-port':  27015
  'smtp-ip':    127.0.0.1
  'smtp-port':  1025
```

## Example playbook

    - hosts: servers
      roles:
         - { role: elao.mailcatcher }

# Licence

MIT

# Author information

ELAO [**(http://www.elao.com/)**](http://www.elao.com)
