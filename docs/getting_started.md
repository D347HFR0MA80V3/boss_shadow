# Getting Started

## Project Goals

Boss Shadow is a multi technology project combining cloud compute, splunk enterprise,
and ansible automation to deploy out a working Splunk Boss of the SOC CTF competition.

Our minimum viable product (mvp) will initialize a secure AWS environment, install
Splunk on one or more Linux EC2 instances, install BOTS components and data, and
finally distribute login credentials to players and teams.

## Required Technology and Installs

- Ansible >= 2.8
- Boto3 ... Required for your local host to interact with AWS account
- Mitogen 2.8 ... No need to manually install as the plugin is included
- Established AWS account ... This project does not establish one for you