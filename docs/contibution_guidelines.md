Contribution Guidelines
=======================

Regardless of skill sets and expierience, don't hesitate to reach out and ask how to contribute. Basic guidelines are below but are no means a limitation to contribution. Any contibutions will be reviewed and style or sytax edits can be provided.

Project Owner Github

https://github.com/D347HFR0MA80V3

Shad0w Synd1cate Discord

https://discord.gg/x547Wmb


Table of Contents
-----------------

* [Project Goals](#project%20goals)
* [General](#general)
    * [Documentation](#documentation)
        * [Markdown](#markdown)
    * [Ansible](#ansible)
        * [YAML](#yaml)
        * [Role Structure](#role%20structure)

Project Goals
-------------

Boss Shadow is a project combining cloud compute, splunk enterprise, and ansible automation to deploy out a working Splunk Boss of the SOC CTF competition.

Our minimum viable product (mvp) will initialize a secure AWS environment, install Splunk on one or more Linux EC2 instances, install BOTS components and data, and finally distribute login credentials to players and teams.

Additionally, provide playbooks to teardown all of the components after the CTF has been completed.

General
=======

Documentation
-------------

Markdown
--------

Ansible
-------

YAML
----

Some of the initial development on this project was done in Visual Studio Code with the Ansible extension installed. However, contributing developers can use any number of linters and YAML tools as roles will get integrated with Travis CI and Ansible syntax will be checked at the code commit phase.

Single new line separations between tasks or major blocks of code in roles or playbooks are highly appreciated but not enforced. Project code reviewers can provide feedback on code organization and cleanliness. 

Role Structure
--------------

The roles already framed in the project were initialized from the Ansible 2.9 role init command. The only paticular practice recommended is how to use the main file of `roles/<role_name>/tasks/`. For our project it is preferred that the only code that lives in main, is `include:` statements that point to other tasks files in the same directory. The includes should utilize tags that are named after the corresponding task file.

Example `tasks/main.yml`

```yml
- include: foo.yml
  tags: foo

- include: bar.yml
  tags: bar

- include: baz.yml
  tags: baz
```

These includes would not only tell the role to load these tasks at runtime but also control the run order of segments of code. The tags allow testers to target single tasks or pieces of code from the command line to save development cycles.

Example: `ansible-playbook role.init_aws_env.yml --tags 'foo,baz'` would run the launch init_aws_env role playbook but isolate the run to the tasks with the foo and baz tags.
