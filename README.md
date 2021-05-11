------
# 4DEVOP PROJET - ZAKI & LAMKADEM
-- Master Of Science 1 - SUPINFO International University.
-- 2021.
-------
A repository of: 
POZOS WEBAPP Deployment using Docker-compose, Jenkins, Ansible, Anchore, Arachni ngrok + MONITORING system using DataDog. 


Files:

- Dockerfile: the docker for the build step on the Jenkinsfile.
- Jenkinsfile: The pipeline for Jenkins.
- docker-compose.yml: the docker-compose used on the Jenkinsfile.
- hosts: the hosts file for the Ansible PLAYBOOKS "install.yml" & "student_list.yml"
- index.php: the home index of the POZOS WEBSITE.
- install.yml: Ansible PLAYBOOK for all the set up needed for the good deployment of the pozos website.
- student_age.json: The data content for the Dockerfile.
- student_age.py: The python API of Student_list.
- student_list.yml: Ansible PLAYBOOK of the deployment of POZOS website.


