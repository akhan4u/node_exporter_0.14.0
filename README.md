node_exporter_0.14.0
=========

This role is used to install Prometheus node_exporter (0.14.0) for monitoring the target systems.  
[Node Exporter](https://prometheus.io/docs/guides/node-exporter/) is the most popular exporter to use when you start monitoring 
your systems with Prometheus.

Requirements
------------

*  We need Ansible software to be installed in order to use these role, means Role can be run from any machine that have Ansible installed on.

Here are the steps to install the Ansible on Ubuntu 14.04 LTS:

	sudo apt-add-repository -y ppa:ansible/ansible  
	sudo apt-get update  
	sudo apt-get install -y ansible


*  Connectivity from Ansible Control server to Remote nodes.

Role Variables
--------------

*  Username with which you need to run node_exporter.
	      
	         monitoring_user: ubuntu


Example Playbook
----------------

Sample playbook leveraging this role:

  	- hosts: "{{ host_name }}"
    	  gather_facts: yes
      	  become: true
    	  tags: inventory
    	  vars:
      	    - monitoring_user: ubuntu
    	  roles:
      	    - node_exporter_0.14.0
	    
It will also place the systemd [service](templates/node_exporter.service) file.
                        
           systemctl start node_exporter.service
           systemctl status node_exporter.service  

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Amaan Khan  
Email: Amaan.ngp@gmail.com  
LinkedIN: https://www.linkedin.com/in/amaan-khan-linux-ninja/  
Twitter: @Amaankhan4you  
