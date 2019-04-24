..... Setup Docker on the Server with VM running nginx .........


Step 1  -  Signup for a free cloud account using 
		
		https://aws.amazon.com/free
				OR
		https://cloud.google.com/free


Step 2 - Create a VM-instance

	-Login in your Cloud account(GoogleCloud/AWS/DigitalOcean)
	-Go to Computer Engine > VM instances > Create New Instance

Step 3 - Installing Ansible at local host
	
	RHEL/CENTOS - "yum install ansible" #yum command will resolve all the dependency by itself

	UBUNTU -     sudo apt-get update
                     sudo apt-get install software-properties-common
	             sudo apt-add-repository ppa:ansible/ansible 
	             sudo apt-get update
                     sudo apt-get install ansible

STEP 4 - Setting up Configuration for Local Instance/VM instance

	GOTO > vim /etc/ansible/hosts
	[ec2] # any name can be used
	
	ec2-instance ansible_host=<<ec2-instance-ip>> ansible_user=ec2-user ansible_ssh_private_key_file=/location/of/the/keypair/your-key.pem
