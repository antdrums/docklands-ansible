Building an EC2 instance with a simple node app container served through an nginx container
-------------------------------------------
 This playbook is tested on OS X / Ubuntu 14.04

-- Requirements
* You must have ansible installed and configured on the system running these scripts. Read the ansible documentation for more info
* You must have Boto configured on the system running these scripts, with your AWS credentials either in the boto config files or on the appropriate environment variables. Read the boto docs for more info.

If running the playbook to set up an EC2 instance, you need to run : 
```
        ansible-playbook -vv -i hosts site.yml
```
Once done, you can check the results by browsing to http://<instance IP / fqdn>
You should see a simple test page 

This playbook uses the boto configuration on the machine it is run from, and performs the following steps :
- Creates a new SG if required, and sets simple http/https ingress and all ports as egress
- Creates a new key pair and saves it in the user's .ssh directory
- Creates the EC2 instance (in this case it's a t2.micro, ubuntu 14.04 instance)
- Adds the instance to the in-memory inventory
- Connects to the new instance using the keypair created and then 
  - Installs docker, docker-py etc
  - Pulls and runs the node image
  - Pulls and runs the nginx image


In order to test this, it's a good idea to change the **env** variable in **site.yml**. This ensures that a new system is created from scratch. If you try to run this script on an env that's already been run by someone else, you might need to get the .pem file from them and store it in your **~/.ssh** folder. 
