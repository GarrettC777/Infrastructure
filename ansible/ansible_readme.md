The following YML files can be found in this directory:
- ssh.yml
-webserver.yml

The ssh.yml performs the following actions:
 - Install system updates and upgrades for ubuntu system.
 - Back up a copy of the sudoers file.
 - Add the group "cit480" to the server and add that group to the sudoers file.
 - Create group member users for the cit480 group.
 - Copy the public keys for each member from a local directory to the remote host.
 
 To run this ssh.yml against the EC2 instance to perform these actions, the following line must be added to the ansible host file:
 ```
<AWS Public DNS> ansible_user=ubuntu ansible_ssh_private_key_file=/path/to/aws/private_key
 ```
 This line uses the ubuntu account and the AWS private key for that account to SSH to perform the actions listed above on the EC2 instance.
The reason that this private key is needed is because we have yet to add the users and public keys for those users, but once this playbook
is run, we will be able to use those users and their private/public keys to authenticate for the playbooks to run.  After the ssh YML file has been
executed, we move on to the webserver.yml file.

The webserver.yml performs the following actions:
- Add the php repositories
- Update package list
- Install Apache2 and PHP, including php dependencies
- Start the Apache service
- Copy the groups html files to the server index.

At this point, we can change that earlier host file configuration to use oru personal private keys and users that were created from the earlier ssh.yml script using this variation:
```
<AWS Public DNS> ansible_user=<MY_USER> ansible_ssh_private_key_file=/path/to/MY/private_key
 ```
Last but not least, to run this command, we must run the ansible-playbook with an additional variable.  The command should look like this:
```
ansible-playbook webserver.yml --extra-vars "ansible_sudo_pass=<my_password>"
 ```
 At this point, the web server is available to be seen at the domain chosen as long as the correct routing has been implemented and in our case
 it would be found at "www.thegroupseniordesign.tech", our test EC2 website.
 
 Last but not least, once these playbook actions have been performed, all that is left to do is run certbot and get the TLS certificate for HTTPS.