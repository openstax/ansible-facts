ansible-facts
=========

In the event that the sudo command is not available this role does some basic facts gathering. This allows our various roles to work in different enviornments

Requirements
------------

N/A

Role Variables
--------------

| Name                 | Default Value | Description                                             |
| -------------------- | ------------- | ------------------------------------------------------- |
| `facts_is_darwin`    | true/false    | sets the value to true if OS is OSX else false          |
| `facts_is_debian`    | true/false    | sets the value to true if OS is debian else false       |
| `facts_is_localhost` | true/false    | sets the value to true if host is localhost             |
| `facts_is_remote`    | true/false    | sets the value to true if `facts_is_localhost` is false |

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-facts, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
