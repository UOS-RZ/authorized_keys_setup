# Ansible Role to Add Unix User Accounts

> ‼️  This role is made specifically for Osnabrück University.

This role sets up SSH keys.

## Dependencies

This role requires the general community collection:

```
ansible-galaxy collection install community.general
```

## Role Variables

Have a look at the [defaults](defaults/main.yml) to see what variables you can set.

You will need to specify the variable `admins` as a list of usernames.

## Example Playbook

Just add the role to your playbook and specify your template:

In your `requirements.yml`:
```yaml
- src: https://github.com/UOS-RZ/authorized_keys_setup.git
  scm: git
  version: main
```

An example playbook to create two admin unsers and detele all other users:
```yaml
- hosts: all
  become: true
  roles:
    - role: authorized_keys_setup
      admins:
        - lolek
        - bolek
```


## License

[BSD-3-Clause](LICENSE)
