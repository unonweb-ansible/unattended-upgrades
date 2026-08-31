ABOUT
=====

A radically simple Ansible role for apt **unattended-upgrades**
- State: Testing/Production
- System: Debian

PLAYBOOK
========

```yml
# unattended-upgrades
  - ansible.builtin.import_role:
      name: unattended-upgrades
    vars:
		unattended_upgrades_config_vars:
			periodic_autoclean_interval: 7
			mail: admin@example.net
			origins_pattern:
			# debian
			- "origin=Debian,archive=stable"
			- "origin=Debian,archive=stable-updates"
			- "origin=Debian,archive=stable-security"
			# third party repos
			- "origin=${distro_id},codename=${distro_codename}"
			# code
			- "origin=code stable,archive=stable,site=packages.microsoft.com"
			# spotify
			- "origin=Spotify LTD,archive=stable"
			# firefox
			- "site=packages.mozilla.org"
			# signal
			- "site=updates.signal.org"
			mail_report: "only-on-error"
```
