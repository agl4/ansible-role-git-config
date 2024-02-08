# Git-config

[![Molecule testing](https://github.com/agl4/ansible-role-git-config/actions/workflows/ci.yml/badge.svg)](https://github.com/agl4/ansible-role-git-config/actions/workflows/ci.yml)

Setting **global** git configurations. Equivalent to `git config
--global NAME VALUE`. It simply feeds the `git_config` Ansible module.

## Requirements

See dependencies.

## Role Variables

This is a sample variable structure used by this role:

```yaml
    git_global_config:
      - name: user.email
        value: agl4@example.com
      - name: user.name
        value: Attila GOLONCSER
        state: present
      - name: pull.rebase
        value: "False"
        state: absent
```

### `git_global_config`

A list of name/value pairs to set as global configuration.

### `git_global_config.item.name`

Name of the configuration option.

### `git_global_config.item.value`

Value of the configuration option.

### `git_global_config.item.state`

State of the configuration option. Default: `present`.

## Dependencies

The role `agl4.git` is set as dependency for installing git in
your environment, which is not done in this role for being able to run
it at any time without escalated privileges.

## Example Playbook

```yaml
  - hosts: localhost
    vars:
      git_global_config:
        - name: pull.rebase
          value: "False"
        - name: user.email
          value: agl4@example.com
        - name: user.name
          value: Attila GOLONCSER
    roles:
       - agl4.git_config
```

## License

BSD

## Author Information

[@agl4](https://github.com/agl4)
