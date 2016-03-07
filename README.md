ansible-role-type
=========

this role manages cron and mount.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: type
           mounts:
             /var/hubcron:
               state: mounted
               src: google-v3a:/vol/vola0322/cron
               fstype: nfs
               opts: defaults
             /opt/eis_cm_repos:
               state: mounted
               src: 8.8.8.8:/vol/vola0321/DI_AHS
               fstype: nfs
           crons:
             check_file:
               name: check_file_stat
               minute: 0
               job: "test -f /tmp/test"
             check_dir:
               name: "check dirs"
               hour: 0
               job: "ls -alh > /dev/null"

License
-------

BSD

Author Information
------------------

Elvis Cai
