# Ansible Elastic Playbook
 
This playbook is for setting up version 7.2 OSS of the Elastic Stack on a remote server. 

Based on the ansible-elk-playbook repo by [Daniel Berman]

## Notes and requirements

 - The playbook was built and tested on Ubuntu 18.04 VMs, for Elastic versions 7.2 OSS 
 - You will need Ansible installed and running
 - Playbook is currently configured to set up the Elastic stack together with Metricbeat for server perf monitoring. There is a role for Filebeat as well. You just need to add the Filebeat role to your [site.yml] file.
 
 ## Instructions
 
 1. Edit your Ansible hosts file ('/etc/ansible/hosts') and add an 'elkservers' entry for the server you wish to install Elastic on. You can of course name the host any way you want, this is just an example. 
 2. Verify connectivity to the Elastic server.
 3. In the terminal on the machine hosting Ansible, clone this repo.
 4. Cd into the directory, and run:
 `ansible-playbook -K site.yml`
 5. It will prompt you for a password. This password is so that the remote_user can sudo in order to run the playbook.
 
 The plays in the playbook will run on the target server, installing Elastic and the specified beats shippers. 
 
[site.yml]: https://github.com/IanMoroney/Ansible/blob/master/ansible-elk-playbook/site.yml

[Daniel Berman]: https://github.com/DanielBerman/ansible-elk-playbook
