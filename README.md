# fractalcells

Launch: 2015-07-24

Documentation: to be written^Wimproved.

Please see [the Fractal cells website](http://www.fractalcells.com) for the "Why" and "What".
This README is, for the time being, exclusively about the "How"

## Requirements

You may want to use the following software, and know your way around them before evaluating
`fractalcells || hosting singularity':

1. FreeBSD
1. One ZFS pool.
1. Ansible

## Howto

```
    git clone https://bitbucket.org/fractalcells/fractalcells.git
    cd fractalcells
    cat group_vars/*.example > group_vars/your_firm_name
    vim group_vars/your_firm_name 		# edit all the things
    cp hosts.example > hosts
    vim hosts 					# edit all the things
    ansible-playbook -i hosts site.yml --check
    ansible-playbook -i hosts site.yml
```
Then, do this:

```
    backup and remove the root private keyfrom the {{ certificate_authority }}/root/private directory
    dump on usb key
    lock in safe
    bury safe in garden
    protect safe with dog.
```

If you know what you're doing: you're done now.
If not: we do offer paid support.


## Next Steps

1. Do all the things.

## Powered By

(Implemented already)

1. [FreeBSD](https://www.freebsd.org)
1. [ansible](https://www.ansible.com)
1. [iocage](https://github.com/pannon/iocage)
1. [OpenSMTPD](https://www.opensmtpd.org)
1. [PostgreSQL](https://www.postgresql.org)
1. [OpenLDAP](https://www.openldap.org)

(Work in Progress)

1. [OpenVPN](https://www.openvpn.org)
1. [Redmine](https://www.redmine.org)
1. [Zabbix](https://www.zabbix.org)
1. [GitLab](https://www.gitlab.org)
1. [Jenkins](https://www.jenkins-ci.org)
