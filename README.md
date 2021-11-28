# ansible-fwknop-server

Ansible role to setup a [fwknop](https://www.cipherdyne.org/fwknop/) server also creating config files for its clients.  This works on Ubuntu and Arch Linux based linux systems.

## Usage

Create a playbook with your tasks, and include the role.
The simplest configuration consists of:

```yaml
- name: Simple Example
  hosts: localhost
  roles:
    - role: ansible-fwknop-server
  vars:
    fwknop:
      domain: example.org
      resolve_url: XXXXXXXXXX
      stanzas:
        - name: test1
          timeout: 30
          ports: 
            - number: 43023
              proto: udp
      clients:
        - name: client1
          client_number: 1
          mobile: True
          user: user1
```

