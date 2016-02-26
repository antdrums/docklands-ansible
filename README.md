Building an EC2 instance with a simple node app container served through an nginx container
-------------------------------------------
 This playbook is tested on OS X / Ubuntu 14.04

## Requirements
* You must have ansible installed and configured on the system running these scripts. Read the ansible documentation for more info
* You must have Boto configured on the system running these scripts, with your AWS credentials either in the boto config files or on the appropriate environment variables. Read the boto docs for more info.

If running the playbook to set up an EC2 instance, you need to run : 

        ansible-playbook -vv -i hosts site.yml

Once done, you can check the results by browsing to http://<instance IP / fqdn>
You should see a simple test page 
