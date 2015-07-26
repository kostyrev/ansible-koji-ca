Role Name
=========

This role installs and configures CA for the koji setup.
This is one the the koji- roles which configures whole koji stack.
Roles are:

 * koji-db (https://galaxy.ansible.com/list#/roles/4459)
 * koji-ca (https://galaxy.ansible.com/list#/roles/4460)
 * koji-web (https://galaxy.ansible.com/list#/roles/4456)
 * koji-kojira (https://galaxy.ansible.com/list#/roles/4457)
 * koji-builder (https://galaxy.ansible.com/list#/roles/4461)
 * koji-hub (https://galaxy.ansible.com/list#/roles/4462)

For example of all-in-one setup go to https://github.com/kostyrevaa/ansible-koji-infra

Requirements
------------

This role will work on:
* Red Hat 6
* CentOS 6

Role Variables
--------------

There are some variables in de default/main.yml which can (Or needs to) be changed/overriden:

* `ca_name`: This is the name of CA. Default is koji.

* `ssl_cnf_owner`: This is the owner of ssl.cnf config file. Default it is root.

* `ssl_cnf_group`: This is the group of ssl.cnf config file. Default it is root.

* `ca_root_path`: This is the path for CA directory structure that will be created by this role. Default is /etc/pki/koji.

* `countryName_default`: This is the default countryName that goes into CA's certificate. Default is RU.

* `stateOrProvinceName_default`: This is the default stateOrProvinceName that goes into CA's certificate. Default is Moscow.

* `localityName_default`: This is the default localityName that goes into CA's certificate. Default is Moscow.

* `organizationName_default`: This is the default organizationName that goes into CA's certificate. Default is My company.

* `organizationalUnitName`: This is the organizationalUnitName that goes into CA's certificate. Default is IT.

* `koji_ca_emailAddress`: This is the emailAddress that goes into CA's certificate. Default is info@example.org.

* `koji_ca_certs2issue`: This is the hash of certificates that is to be issues by this CA. Default hash consists only from kojira. It's sufficient if you want all parts of koji setup to reside only on one host.


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: koji_ca
      roles:
         - koji-ca

License
-------

GPLv3

Author Information
------------------

Send your suggestions and pull requests to https://github.com/kostyrevaa/ansible-koji-ca.
When send PR make sure your changes are backward-compatible. Test your changes to role with https://github.com/kostyrevaa/ansible-koji-infra
