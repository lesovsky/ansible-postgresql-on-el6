### README: install-postgresql-on-el

Features:
- supported distributions: 6 and 7 versions of Redhat, CentOS, Scientific Linux.
- Oracle Linux also supported but uses RHEL repositories.
- supported PostgreSQL versions: 8.4, 9.0, 9.1, 9.2, 9.3, 9.4.
- allows specify users and databases which would be created after install.
- ability to determine a set of postgresql.conf parameters and absense postgresql.conf template. Template is not used due to the fact that the postgresql.conf differs from version to version on a set of parameters.
- ability to specify another cluster directory and setup symlink into /var/lib/pgsql/x.y/data location.
- ability to specify extension list for created databases (only for versions >= 9.0).

Known issues:
- RHEL 6: packages from pgdg repo does not install due to repo configuration parsing error. Workaround: replace $releasever variable to your specific release version. This issue does not occurs on the others distributions.
- RHEL 6: posqtgresqlXY-contrib doesn't install due to dependency error. In my case, this may be caused by the use of an unregistered RedHat distribution and unofficial third-party repositories. On the Oracle Enterprise Linux this issue does not occur.

Todo:

How-to use:
- download repo with git clone;
- cd into role directory;
- change hosts: variable in role.yml;
- start ansible-playbook with role.yml and your inventory file.
```
ansible-playbook -i /etc/ansible/staging role.yml
```
