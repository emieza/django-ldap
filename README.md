
# django-ldap

How to use Django with LDAP

https://pythonhosted.org/django-auth-ldap/index.html


## Prerequistes

Install an LDAP server as slapd in your machine and initialize a DIT.
It can be easily achieved in Ubuntu using:

    # dpkg-reconfigure slapd

Also using a web editor for LDAP as phpldapadmin is recommended.

Build a directory tree according your needs.


## Using Ubuntu

You need to install certain development libs:

    # apt-get install libssl-dev libsasl2-dev libldap2-dev python-dev

Also using virtualenv is convenient.

Install ldap package in your environment:

    $ pip install django-auth-ldap

## Configure your app

Add that lines to settings.py

```python
# LDAP auth

AUTHENTICATION_BACKENDS = (
    'django_auth_ldap.backend.LDAPBackend',
    'django.contrib.auth.backends.ModelBackend',
)

AUTH_LDAP_USER_DN_TEMPLATE = "uid=%(user)s,ou=usuaris,dc=enric,dc=local"
```


