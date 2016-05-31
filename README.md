ansible-role-authconfig
=========

Configure authentication against Active Directory using sssd, adcli, and authconfig.

This role joins to and AD domain using adcli.

Requirements
------------

Active Directory Domain with tls/LDAP and Kerberos.

Cent/RedHat/EL 6 and 7 are supported at this time. Only slight modifications should
be needed to support Ubuntu.

This role does NOT configure sudo.

Role Variables
--------------

### Required

| variable | description | default |
|----------|-------------|---------|
| authconfig_domain | AD domain | 'example.com' |
| authconfig_realm  | AD Realm  | 'EXAMPLE.COM' |
| authconfig_windomain | AD Windows Domain | "EXAMPLECOM" |
| authconfig_computer_ou | Where to create the computer object in AD | 'ou=computers,dc=example,dc=com' |
| See test.yml for example of hostvars |||
| hostvars['localhost']['authconfig_sssd_name'] | Name of user to use to join domain | '' |
| hostvars['localhost']['authconfig_sssd_pass'] | Password to use to join domain | '' |
| | |
| authconfig_access_groups | Array of groups that have access to the host | [ ] |
| authconfig_access_users  | Array of users that have access to the host | [ ] |

### Optional

| variable | description | default |
|----------|-------------|---------|
| authconfig_debug_mode | Enable debug logging | false |
| authconfig_debug_level | debug logging level 0-9 | 3 |


Example Playbook
----------------

See test.yml

License
-------

BSD

Author Information
------------------
Jon Bidinger based on work by:
   Jeff Gibson, Dan Rue and Adrian Herrera
