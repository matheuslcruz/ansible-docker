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
    docker ps -qa

Put all containers created by the stack into host groups in the inventory hosts.ini:

    [container]
    a812d33517ed
    f1b4dc489e59

TEST CONTAINERS
--

    ansible-playbook -i hosts.ini setup-container.yml

UNDEPLOY STACK
--

    ansible-playbook -i hosts.ini undeploy-stack.yml

REMOVE CONTAINERS
--

See: https://github.com/moby/moby/issues/32620

    ansible-playbook -i hosts.ini remove-containers.yml
