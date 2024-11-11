Role Name
=========

The ssh_config role help you to configure ssh on your machines.

Requirements
------------

A set of machines with a root access!

Role Variables
--------------

To define whether it have to restart the ssh service or not after applying the changes:

  sshd_service_restart

Dependencies
------------

No dependencies. All of the used dependencies are builtin. 

Example Playbook
----------------

      - hosts: all
        become: yes
        tasks:
          - name: configure ssh
            include_role:
              name: rezachalak.user_ssh_toolbox.ssh_config
            vars:
              sshd_service_restart: true

        

License
-------

BSD

Author Information
------------------

