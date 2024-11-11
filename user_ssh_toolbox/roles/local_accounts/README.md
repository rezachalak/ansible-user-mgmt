Role Name
=========

The Local_accounts role help you to configure your own users with a single dictionary.

Requirements
------------

A set of machines with a root access!

Role Variables
--------------

A list of users with the following keys defined:

local_users
  - name
    shell
    userid
    expiry_date
    home
    groups
    authorized_keys

Dependencies
------------

No dependencies. All of the used dependencies are builtin. 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

      - hosts: all
        become: yes
        tasks:
          - name: Register end of 2024 expiry
            command: date -d '2024-12-31T23:59:59' '+%s'
            register: expiry_r

          - name: Create local accounts
            include_role:
              name: rezachalak.user_ssh_toolbox.local_accounts
            vars:
              local_users:
                - name: local_adm
                  shell: /bin/bash
                  userid: 38000087
                  expiry_date: -1  # No expiry intended
                  home: /home/local_adm
                  groups: 'sudo'
                  authorized_keys: '{{ playbook_dir }}/authorized_keys_local_adm'
        

License
-------

BSD

Author Information
------------------

Reza Chalak <rezachalak.int@gmail.com>