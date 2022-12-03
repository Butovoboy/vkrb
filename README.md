## What is it
This is Egor Malyshev bachelor diploma work.

## Why does this work may be important
During the software development process, a code storage system, a task control system, as well as a system of intra-team interaction are often used. The integration of these three systems is of the greatest interest.

Integration of these three systems can speed up the process of software creation, which is quite important due to the saving of production costs and increasing new features implemetation.

### What does this code do
Here we have one Vagrantfile, that creates virtual machines, one Ansible playbook and four Ansible roles. Vagrantfile starts Ansible playbook, which triggres all other roles. Every role is responsible for some instrument:
- the first role is prerequisties downloads some packets and programsi (like docker) that we will use in the next roles to start applications.
- the secind role starts a code storage system (`Gitlab`)
- the third role starts an intra-team interaction system (`Mattermost`)
- the fourth role starts a task control system (`Redmine`)

And after installation of all of these software you should do some steps by yourself at these instruments web interface.

### How to run this code
