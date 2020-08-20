# Desktop git role

Setting **global** git configuration. Equivalent to `git config --global NAME VALUE`.

## Requirements

Git should be installed on the system.

## Role Variables

This is a sample variable structure used by this role.


    git_global_config:
      - name: pull.rebase
        value: "False"
      - name: user.email
        value: agoloncser@example.com
      - name: user.name
        value: Attila GOLONCSER

### `git_global_config`

A list of name/value pairs to set as global configuration.


## Dependencies

None. However git should be installed on the system. See https://github.com/agoloncser/ansible-role-git for a role that takes care of this.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

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

## License

BSD

## Author Information

https://github.com/agoloncser
