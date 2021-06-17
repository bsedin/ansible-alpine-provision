# Ubuntu common roles for ansible

Create `./library` directory in your ansible project:

```
mkdir ./library
```

And configure `ansible.cfg`:

```
[defaults]
roles_path = ./library
```

Add submodule:

```
git submodule add git@github.com:kressh/ansible-alpine-provision.git library/alpine-provision
```

Use role:

```yaml
---
- hosts: yourserver.io
  remote_user: ansible
  become: true
  roles:
    - alpine-provision
```
