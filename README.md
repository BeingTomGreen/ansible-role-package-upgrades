# beingtomgreen.package_upgrades

A simple role for handling package upgrades on apt and yum/dnf based distributions.

This role supports optionally rebooting Debian and Ubuntu based instances, to determine if a reboot is needed the role checks for the presence of `/var/run/reboot-required file`, however if you use Canonical's Livepatching service you may want to skip this.

## Installation & usage

Given that Galaxy seems to have abandoned roles, I suggest referencing this repository directly in your projects `requirements.yml`:

```yaml
---

roles:
  - name: beingtomgreen.package_upgrades
    src: https://github.com/BeingTomGreen/ansible-role-package-upgrades.git

collections: []
```

You can then install it alongside your other requirements as normal:

```bash
ansible-galaxy install -r requirements.yml
```

Now you're free to use it within your project:

```yaml
---

- hosts: debian,ubuntu
  become: true

  roles:
    - role: beingtomgreen.package_upgrades
      vars:
        package_upgrades_reboot: true
        package_upgrades_autoremove: true
```

## Role Variables

See [`defaults/main.yml`](defaults/main.yml) & [`vars/main.yml`](vars/main.yml) for more details.

## Requirements

None.

## Dependencies

None.

## License

[MIT](LICENSE)

## Author Information

[Tom Green](https://github.com/BeingTomGreen)
