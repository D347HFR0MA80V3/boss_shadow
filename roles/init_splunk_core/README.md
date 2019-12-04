init_splunk_core
================

A role that will initialize (build) Splunk Enterprise on the instances that have
been built in your cloud environment.

Requirements
------------

- RHEL like compute instance(s)
- Working connection from compute instance to splunk.com to download the bits

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Launch Playbook
-----------------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: "{{ target }}"
  become: yes
  become_user: root
  become_method: sudo
  gather_facts: yes
  vars_prompt:
    - name: "target"
      prompt: "Target group(s) or host(s)?"
      private: no
      default: all
  roles:
    - init_splunk_core
```

License
-------

MIT

Author Information
------------------

- Lee Goodrich https://github.com/D347HFR0MA80V3
