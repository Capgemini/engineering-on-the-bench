# Ansible Examples

Ansible is an open source automation platform. Ansible can help you with configuration management technology used to provision, application deployment, task automation and manage compute infrastructure across cloud, virtual, and physical environments. Ansible uses SSH which is assumed to be installed on all the systems you want to manage.

Ansible is available for free and runs on Linux, Mac or BSD. 

## Ad-Hoc Commands(For the quick check)

 ###### To check all my inventory hosts are ready to be managed by ansible
 ```
 $ansible all -m ping
 ```
 
 Note: The "all" keyword is for all of the hosts in your inventory.
 
 ###### To target hosts in a specific group you enter the group name instead of all.
 ```
 
 $ ansible nagios -m ping -u deploy
 ````
 ###### To run the uptime command on all the hosts in the web group
 ```
 
 $ ansible web -m command -a "uptime"
 ```
 ###### To collect and display the discovered for the localhost
 ```
 
 $ ansible localhost -m setup
 ```
 ## Inventory
 
 Inventory is a collection of hosts(nodes) against which Ansible can work with.
 
 * Hosts 					
 * Inventory-specific data
 * Group Sources 
 * Static or dynamic
 
 ###### To test the connection with target hosts
 ```
 $ ansible all -i hosts -u vagrant -m ping
 ```
 
 ###### To setup using module
 ```
 $ ansible all -i hosts -u vagrant -m setup
 ```
 ###### To config webserver using module
 ```
 $ ansible webserver -i hosts -u vagrant -m yum -a "name=httpd state=present" -b
 ```
 
 ###### To Rollback
 ```
 $ ansible webserver -i hosts -u vagrant -m yum -a "name=httpd state=absent" -b
 ```
 
 
 
 
 ## Variables
 
 **file**: Adirectory should exist
 
 **yum**: A package should be installed
 
 **service**: A service should be running
 
 **template**: Render a config file from a template
 
 **get_url**: Fetch an archive file from a URL
 
 **git**: Clone a source code repository
 
 
 ## Handler Tasks
 
 Handlers are special tasks that run at the end of the play if notified by another task.
 
 if a configuration file gets changed notify a service restart task it needs to run

## PLAYS &PLAYBOOKS

	Plays are ordered sets of tasks to execute against host selections from your inventory.
	
	A Playbook is a file containing one or more plays.