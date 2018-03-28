Ansible Docker
==

Base project using Ansible, Docker-Py and Compose.
--

SETUP
--

Copy the following files and change the values according to your configuration:

    cp -v group_vars/all.sample group_vars/all
    cp -v hosts.ini.sample hosts.ini

DEBUG ANSIBLE
--

    ansible-playbook -i hosts.ini debug-ansible.yml

DEPLOY STACK
--

    ansible-playbook -i hosts.ini deploy-stack.yml

TEST CONTAINERS
--

Download [docker.py](https://github.com/ansible/ansible/blob/devel/contrib/inventory/docker.py) to use dynamic inventory.

    ansible-playbook -i docker.py ping-container.yml

UNDEPLOY STACK
--

    ansible-playbook -i hosts.ini undeploy-stack.yml
