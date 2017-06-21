#Ansible Essentials

Ansible is an open source automation platform. Ansible can help you with configuration management technology used to provision, application deployment, task automation and manage compute infrastructure across cloud, virtual, and physical environments. Ansible uses SSH which is assumed to be installed on all the systems you want to manage.

Ansible is available for free and runs on Linux, Mac or BSD. 

#Ad-Hoc Commands(For the quick check)
 To check all my inventory hosts are ready to be managed by ansible
 
 $ansible all -m ping
 
 Note: The "all" keyword is for all of the hosts in your inventory.
 
 To target hosts in a specific group you enter the group name instead of all.
 
 $ ansible nagios -m ping -u deploy
 
 To run the uptime command on all the hosts in the web group
 
 $ ansible web -m command -a "uptime"
 
 To collect and display the discovered for the localhost
 
 $ ansible localhost -m setup
 
 # Inventory
 
 Inventory is a collection of hosts(nodes) against which Ansible can work with.
 
 >> Hosts 					>> Inventory-specific data
 >> Group Sources 	>> Static or dynamic
 
 To test the connection with target hosts
 
 $ ansible all -i hosts -u {connecting_user} -m ping ( Whether i have a connectivity to target m/c)
 
 e.g., connecting user - vagrant, -m : module
