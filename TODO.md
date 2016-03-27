Various TODO-items:

BUGS:
- too many FIXMEs/TODOs/XXXs remaining
- security settings could in parts be different
- missing secadm rules for redmine
- sshd not yet setup in gitlab jail, portforward or use chroot?
- cert signing could be redone


FEATURE PLANS:

- add proper email server:
  add dovecot to mx jail
  add sieve to mx jail

  add roundcube to internal jail
      roundcube-plugin-sieve

- add proper log analysis

  add elasticsearch/logstash to logging jail ?
  add grafana to internal jail ?

- bump zabbix to 3.0

MISC:
- template jenkins hudson.plugins.git.GitSCM.xml

LOW-PRIORITY:
- integrate design across zabbix/redmine/jenkins/phpldapadmin/phppgadmin
- make fc ipv6 ready -- show-stopper: missing af-to
- make zabbix uids in jails dynamic within some range
  (host\_hostuuid? hostname? iocage var)
