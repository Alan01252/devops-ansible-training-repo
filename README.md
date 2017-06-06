# Devops Training Ansible

The aim of the repository is to act as a starting point for those wanting to get familiar with Ansible.

## Installing

This guide assumings you've got a virtual machine capable of running docker.

- clone this repository and cd to directory
- Log on to virtual machine
- Install docker ( if not installed )
- Install Ansible
- Create centos image
	`docker run -d \\n  --name ssh.pool-1.1.1 \\n  -p 2020:22 \\n  jdeathe/centos-ssh:centos-7`
- Download private key
	`curl -LSs \\n  https://raw.githubusercontent.com/mitchellh/vagrant/master/keys/vagrant \\n  > ~/.ssh/id_rsa_insecure`
- Change permissions of key
	`chmod 600 ~/.ssh/id_rsa_insecure`
- Test SSH connection
	`ssh -p 2020 -i id_rsa_insecure app-admin@127.0.0.1`
- Run playbook
	`ansible-playbook site.yml -i stage`

If everything has worked you should see a hello world message from ansible on the server
 

