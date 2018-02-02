ansible-facts
=========

[![Build Status](https://travis-ci.org/openstax/ansible-facts.svg?branch=master)](https://travis-ci.org/openstax/ansible-facts)

In the event that the sudo command is not available this role does some basic facts gathering. This allows our various roles to work in different enviornments

Requirements
------------

N/A

Role Variables
--------------

| Name                            | Default Value    | Description                                                                      |
| ------------------------------- | ---------------- | -------------------------------------------------------------------------------- |
| `users_app_owner`               | undefined        | used by later values to determine if ansible_user is the owner                   |
| `facts_is_darwin`               | true/false       | sets the value to true if OS is OSX else false                                   |
| `facts_is_debian`               | true/false       | sets the value to true if OS is debian else false                                |
| `facts_is_localhost`            | true/false       | sets the value to true if host is localhost                                      |
| `facts_is_remote`               | true/false       | sets the value to true if `facts_is_localhost` is false                          |
| `facts_shell`                   | n/a              | sets the value depending on the shell detected by ansible                        |
| `facts_user_is_ansible_user`    | true/false       | sets the value to true if `users_app_user` is undefined or false                 |
| `facts_user_is_users_app_owner` | true/false       | sets the value to true if `facts_user_is_ansible_user is false                   |
| `facts_group`                   | n/a              | sets the value to www-data if `facts_user_is_users_app_owner` else omits         |
| `facts_profile_name`            | .bashrc          | sets value to .bashrc unless osx then .bash_profile                              |
| `facts_user`                    | n/a              | sets the value to `users_app_owner` if `facts_user_is_users_app_owner else omits |
| `facts_user_home`               | ansible_env.HOME | sets the users home directory                                                    |
| `facts_user_profile`            | n/a              | sets the path to the .bashrc or .bash_profile                                    |

Dependencies
------------
N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - openstax.facts

License
-------

GPLv2

Development & Testing
---------------------

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing; the role is unit tested using
[Testinfra](http://testinfra.readthedocs.io/) and
[pytest](http://docs.pytest.org/).

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)

To run the role

```bash
molecule test
```
