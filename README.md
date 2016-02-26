ansible-role-authconfig
=========

Configure authentication against Active Directory using sssd.

Note that versions of ansible-role-authconfig < 1.0.0 use nslcd and nscd, and
are maintained in the `nslcd` branch.

Requirements
------------

Active Directory Domain with tls/LDAP and Kerberos.

Only Ubuntu 14.04 is supported at this time.

This role does NOT configure sudo.

Role Variables
--------------

### Required

| variable | description | default
|----------|-------------|---------
| `ldap_bind_user` | LDAP bind username | none
| `ldap_bind_pass` | LDAP bind user password | none

### Optional

| variable | description | default
|----------|-------------|---------
| `authconfig_debug_mode` | Enable sssd debug logging | false
| `base_dn` | LDAP base DN | 'dc=foobar,dc=com'
| `domain` | LDAP domain name | 'foobar.com'
| `servers` (list) | AD servers | 'ad1.foobar.com, ad2.foobar.com'
| `access_groups` (list) | AD groups allowed to ssh into the host | 'foo_bar'
| `access_users` (list) | AD users allowed to ssh into the host | ''
| `realm` | Kerberos realm | 'FOOBAR.COM'
| `windomain` | AD domain short name | 'FOOBAR'

Example Playbook
----------------

See test.yml

Testing
-------

- LDAP_BIND_USER
- LDAP_BIND_PASS

License
-------

BSD

Author Information
------------------

Jeff Gibson, Dan Rue and Adrian Herrera
