ldap-ssh-pubkey
=========

A simple Ansible role to configure LDAP logins with SSH public keys.

Requirements
------------

A Samba or Active Directory server is assumed to be already set up with an
account that has the necessary priviledges to join a computer to the domain.

Role Variables
--------------

* `ad_access_filter`: String. See the default, or search the web for "ad_access_filter" or "ldap_access_filter" for more complicated examples.
* `sudo_groups`: Array. A list of groups that are allowed to sudo root on this host.
* `joiner_account`: String. The name of the account that has the necessary priviledges to join a computer to the domain.
* `joiner_password`: String. The password for the `joiner_account`.
* `directory_name`: String. The name of the directory. Must be reachable via ICMP PING.
* `ldap_pubkey_field`: String. The LDAP field that contains users' public keys. Defaults to `sshPublicKey`.

Dependencies
------------

Python and pip need to be installed on the remote machine. Recent Amazon Linuxes fulfill this dependency.
This play installs the `pexpect` pip package, because it uses `expect` to enter the password.

License
-------

MIT
