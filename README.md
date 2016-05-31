ansible-role-authconfig
=========

Configure authentication against Active Directory using sssd, adcli, and authconfig.

This role joins the domain using adcli.

Requirements
------------

Active Directory Domain with tls/LDAP and Kerberos.

Cent/RedHat/EL 6 and 7 are supported at this time. Only slight modifications should
be needed to support Ubuntu.

This role does NOT configure sudo.

Role Variables
--------------

### Required

| variable | description | default
|----------|-------------|---------
| authconfig_domain | AD domain | 'example.com' |
| authconfig_realm  | AD Realm  | 'EXAMPLE.COM' |
| authconfig_windomain | AD Windows Domain | "EXAMPLECOM" |
| authconfig_computer_ou | Where to create the computer object in AD | 'ou=computers,dc=example,dc=com' |
| authconfig_sssd_user | Credstash name of user to use to join domain | 'prod.example_sssdjoin.username' |
| authconfig_sssd_pass | Credstash name of password to use | 'prod.example_sssdjoin.password' |

# An array/list of groups that have access to the host
authconfig_access_groups: []

# An array/list of users that have access to the host
authconfig_access_users: []

### Optional

# Optionally enable sssd debug logging
authconfig_debug_mode: false
authconfig_debug_level: 3


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
