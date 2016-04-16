# fractalcells

Launch: 2015-07-24

Documentation: to be written^Wimproved.

Please see [the #fractalcells website](http://www.fractalcells.com) for the "Why" and "What".
This README is, for the time being, exclusively about the "How"

## Branches

1. `master` - "production" branch. Hopefully as stable as `X.Y-RELEASE`.
1. `develop` - "experimental" branch. Hopefully as stable as `11.0-CURRENT`.
1. `feature/<feature_name>` - bleeding edge feature branches. Use at your own enjoyment.

## Requirements

You may want to use the following software, and know your way around them before evaluating
`fractalcells || hosting singularity`:

1. [HardenedBSD 10.3-RELENG](https://www.hardenedbsd.org/)
1. One ZFS pool.
1. [Ansible](https://www.ansible.com/)
1. [ansible-iocage](https://github.com/fractalcells/ansible-iocage/)

Additionally, we aim to provide `fractalcells || hosting singularity` for
`FreeBSD`. This support, however, has limits: We require you use a version of
`10.3-RELEASE` or later and do not guarantee feature-parity.

For the best support, make sure you're running HardenedBSD builds from the
`10.3-RELENG` or `11.0-CURRENT` branches.

## Howto

```
    git clone https://github.com/fractalcells/ansible-iocage.git
    git clone https://github.com/fractalcells/fractalcells.git
    cd fractalcells
    mkdir library
    ln -s ../ansible-iocage/iocage library/iocage
    cat group_vars/*.example > group_vars/fractalcells
    vim group_vars/fractalcells 		# edit all the things
    cp hosts.example hosts
    vim hosts 					# edit all the things, especially fractalcells section
    cp ansible.cfg.example ansible.cfg
    vim ansible.cfg 				# edit all the things, especially fractalcells section
    ansible-playbook -i hosts bootstrap.yml
    ansible-playbook -i hosts site.yml --check
    ansible-playbook -i hosts site.yml
```

If you know what you're doing: Congratulations, you're done now.
If not: we do offer paid support.


## Next Steps

1. Finish all components.
2. Refactor roles/*/iocage.yml into a cellfactory role.

## Powered By

1. [HardenedBSD](https://www.hardenedbsd.org)
1. [ansible](https://www.ansible.com)
1. [iocage](https://github.com/pannon/iocage)
1. [OpenSMTPD](https://www.opensmtpd.org)
1. [PostgreSQL](https://www.postgresql.org)
1. [OpenLDAP](https://www.openldap.org)
1. [OpenVPN](https://www.openvpn.org)
1. [Redmine](https://www.redmine.org)
1. [Zabbix](https://www.zabbix.org)
1. [Jenkins](https://www.jenkins-ci.org)
1. [GitLab](https://www.gitlab.org)

## fractalcells pkg server

The following is used to spin up and update the `fractalcells` package server visible at `http://pkg.fractalcells.com`:

```
ansible-playbook -i hosts.pkg pkg.yml -t pkg-server
```

Particular `make.conf` settings (see `roles/poudriere/tasks/poudriere.yml`):
```
DEFAULT_VERSIONS=pgsql=9.4
OPTIONS_UNSET=DOCS EXAMPLES MYSQL MYSQL2 MYSQLI APACHE APACHE22 APACHE24 THIN X11 APNG PNGTEST GNUTLS
OPTIONS_SET=PGSQL POSTGRESQL PASSENGER NGINX PNG LDAP LDAPS OPENSSL
```
