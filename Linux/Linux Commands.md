Linux Commands Used

ssh (Jump-Box Username)@(Dynamic Jump-Box IP)

sudo su
-	this changes you to root to not always have to use sudo

apt-get docker.io
-	use if docker.io is not installed
-	hub.docker.com (select a docker image you want)
-	docker pull [username/container image]

docker run -ti [username/docker image] bash

docker container list -a
-	shows what containers you have available

docker start [container name]

docker ps [container name]

docker attach [container name]

cd /etc/ansible/ 

nano pentest.yml
-	https://github.com/papmalakul/ELK-Stack-Project/blob/main/Ansible/pentest.yml
-	change host to your specific [hostname]
-	hostname in etc/ansible/hosts

ansible-playbook [name yml playbook]
-	to run playbook once created

nano elk-playbook.yml
-	https://github.com/papmalakul/ELK-Stack-Project/blob/main/Ansible/elk-project.yml

nano filebeat-playbook.yml
-	https://github.com/papmalakul/ELK-Stack-Project/blob/main/Ansible/filebeat-playbook.yml

nano metricbeat-playbook.yml
-	https://github.com/papmalakul/ELK-Stack-Project/blob/main/Ansible/metricbeat-playbook.yml

