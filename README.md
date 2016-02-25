Building a simple node app, nginx container and deploying them to ec2
-------------------------------------------


These playbooks are meant to be a reference and starter's guide to building
Ansible Playbooks. These playbooks were tested on Ubuntu 14.04

If running the playbook to set up an EC2 instance, you need to 

        ansible-playbook  site.yml

Once done, you can check the results by browsing to http://<instance IP / fqdn>
You should see a simple test page 
