# fedora

Example `playbook.yml`:
```yml
---
- hosts: localhost
  become: true
  connection: local
  roles:
    - { role: default-dirs, tags: ["dirs"] }
    - { role: setup-repos, tags: ["repos"] }
    - { role: packages, tags: ["packages"] }
    - { role: debloat, tags: ["debloat"] }
    - { role: vscodium, tags: ["vscodium"] }
    - { role: alacritty, tags: ["alacritty"] }
    - { role: gnome-extensions, tags: ["gnome-extensions"]}
    - { role: zsh, tags: ["zsh"] }
    - { role: nvidia, tags: ["nvidia"] }
```

Run roles: `ansible-playbook playbook.yml -i inventory.ini --ask-become-pass -v --tags "packages"`