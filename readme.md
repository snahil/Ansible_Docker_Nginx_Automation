..................................Setup Docker on the Server with VM running nginx ............................................

................................................GOOGLE CLOUD PLATFORM..........................................................

Google, is a suite of cloud computing services that runs on the same infrastructure that Google uses internally for its end-user products, such as Google Search and YouTube. Alongside a set of management tools, it provides a series of modular cloud services including computing, data storage, data analytics and machine learning. Registration requires a credit card or bank account details.

Google Cloud Platform provides Infrastructure as a service, Platform as a service, and Serverless computing environments.

In April 2008, Google announced App Engine, a platform for developing and hosting web applications in Google-managed data centers, which was the first cloud computing service from the company. The service became generally available in November 2011. Since the announcement of App Engine, Google added multiple cloud services to the platform.

https://en.wikipedia.org/wiki/Google_Cloud_Platform

........................................................DOCKER.................................................................

Docker is a computer program that performs operating-system-level virtualization. It was first released in 2013 and is developed by Docker, Inc.

Docker is used to run software packages called containers. Containers are isolated from each other and bundle their own application,tools, libraries and configuration files; they can communicate with each other through well-defined channels. All containers are run by a single operating-system kernel and are thus more lightweight than virtual machines. Containers are created from images that specify their precise contents. Images are often created by combining and modifying standard images downloaded from public repositories. 

https://en.wikipedia.org/wiki/Docker_(software)

.........................................................NGINX.................................................................

NGINX is a free, open-source, high-performance HTTP server and reverse proxy, as well as an IMAP/POP3 proxy server. NGINX is known for its high performance, stability, rich feature set, simple configuration, and low resource consumption.

NGINX is one of a handful of servers written to address the C10K problem. Unlike traditional servers, NGINX doesn’t rely on threads to handle requests. Instead it uses a much more scalable event-driven (asynchronous) architecture. This architecture uses small, but more importantly, predictable amounts of memory under load. Even if you don’t expect to handle thousands of simultaneous requests, you can still benefit from NGINX’s high-performance and small memory footprint. NGINX scales in all directions: from the smallest VPS all the way up to large clusters of servers.

https://www.nginx.com/resources/wiki/


//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

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

LocalVM 
[local] # any name can be used
192.168.2.25
192.168.43.105
CloudVM
[ec2] # any name can be used
	 -ec2-instance ansible_host=<
	<ec2-instance-ip>> ansible_user=ec2-user ansible_ssh_private_key_file=/location/of/the/keypair/your-key.pem
					OR

[test]
159.89.104.69  // For adding the ip of cloud vm need to set ssh-id at server side


		setting up sshid 

		step-1 Generating SSH_ID
		       ssh-keygen
		step-2 Copy ssh-id
		       ssh-copy-id root@159.89.104.69
////////////////////////////////////////////////TEST ATL LOCAL AND REMOTE VM//////////////////////////////////////////////////

TESTING AT LOCAL VM
VM - 192.168.2.25(LOCAL_TEST_TARGET_1)
        ![2](https://user-images.githubusercontent.com/16596896/56714378-438ffd80-6752-11e9-9610-c6671f0af967.JPG)
VM - 192.168.43.105(LOCAL_TEST_TARGET_2)
        ![3](https://user-images.githubusercontent.com/16596896/56714381-47238480-6752-11e9-9376-f16de21ffd7b.JPG)

Refrences -

>https://docs.ansible.com/ansible/latest/scenario_guides/guide_gce.html
>https://cloud.google.com/docs/
>https://docs.ansible.com/
>https://docs.ansible.com/ansible/latest/user_guide/playbooks.html
