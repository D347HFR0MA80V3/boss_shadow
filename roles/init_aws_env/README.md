init_aws_env
============

Minimal role to initializea a secure AWS environment that includes EC2 instances
to host Splunk BOTS.

Requirements
------------

- AWS account with generated keys for Ansible to use
- boto3
- Ansible 2.8

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

No other role dependancies at this time.

Launch Playbook
---------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```yaml
- hosts: "{{ target }}"
  become: yes
  become_method: sudo
  vars_prompt:
    - name: "target"
      prompt: "Host that will execute the AWS build commands... defaults to ->"
      private: no
      default: localhost
  roles:
    - init_aws_env
```

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
