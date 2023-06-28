---
title: 'SOP: openQA - System Upgrades'
---

This SOP details the necessary steps for performing a system upgrade on an openQA host.

{% include "contacts_top.md" %}

## Fedora

1. Verify current installation is fully upgraded

    dnf upgrade --refresh

1. Install system upgrade plugin

    dnf install dnf-plugin-system-upgrade

1. Download the upgrade packages for next version

    dnf system-upgrade download --releasever=[newversion]

1. Reboot into offline upgrade mode

    dnf system-upgrade reboot

1. Post-reboot cleanup

    dnf system-upgrade clean
    dnf clean packages

## Post-Upgrade Tasks

These steps may also be necessary in some (but not all) cases.

### Upgrade the PostgreSQL database

1. Install postgresql-upgrade package

    dnf install postgresql-upgrade

1. Upgrade your postgres database

    sudo -iu postgres
    postgresql-setup --upgrade

### Re-apply Rocky branding

1. Obtain the [Ansible openQA deployment repository](https://git.resf.org/infrastructure/ansible-openqa-management)

1. Run the branding related tasks

    ansible-playbook init-openqa-rocky-developer-host.yml -t branding

## References
https://docs.fedoraproject.org/en-US/quick-docs/dnf-system-upgrade/
https://www.makeuseof.com/how-to-upgrade-to-fedora-workstation-36/

{% include "content_bottom.md" %}
