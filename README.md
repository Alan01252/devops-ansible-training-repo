# Devops Training Ansible

The aim of the repository is to act as a starting point for those wanting to get familiar with Ansible.

## Installing

This guide assumings you've got a virtual machine capable of running docker.

- clone this repository and cd to directory
- Log on to virtual machine
- Install docker ( if not installed )
- Install Ansible
- Create centos image
	`docker run -d --name ssh.pool-1.1.1 -p 2020:22 jdeathe/centos-ssh:centos-7`
- Download private key ( public key is already authorised in above image )
	`curl -LSs https://raw.githubusercontent.com/mitchellh/vagrant/master/keys/vagrant > ~/.ssh/id_rsa_insecure`
- Change permissions of key
	`chmod 600 ~/.ssh/id_rsa_insecure`
- Test SSH connection
	`ssh -p 2020 -i ~/.ssh/id_rsa_insecure app-admin@127.0.0.1`
- You should now be inside the box, awesome exit it
	`exit`		
- Run playbook
	`ansible-playbook site.yml -i stage --private-key ~/.ssh/id_rsa_insecure `

If everything has worked you should see a hello world message from ansible on the server
 

