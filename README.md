# Git-config

Setting **global** git configurations. Equivalent to `git config
--global NAME VALUE`. It simply feeds the `git_config` Ansible module.

## Requirements

See dependencies.

## Role Variables

This is a sample variable structure used by this role:

```yaml
    git_global_config:
      - name: user.email
        value: agoloncser@example.com
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

The role `agoloncser.git` is set as dependency for installing git in
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
          value: agoloncser@example.com
        - name: user.name
          value: Attila GOLONCSER
    roles:
       - agoloncser.git_config
```

## License

BSD

## Author Information

(@agoloncser)[https://github.com/agoloncser]
