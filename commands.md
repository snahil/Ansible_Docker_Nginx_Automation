
cmd1- for running "script.yml"
	ansible-playbook script.yum
cmd2- for setting static-ip

     > vim /etc/sysconfig/network-script/ifcfg-enp0s3
     > add - "IPADD=192.168.43.15,BOOTPROTO="STATIC"ONBOOT="YES" "
