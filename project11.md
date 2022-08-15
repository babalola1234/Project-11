# ANSIBLE CONFIGURATION MANAGEMENT – AUTOMATE PROJECT 7 TO 10

### Task
* To Install and configure Ansible client to act as a Jump Server/Bastion Host
* To Create a simple Ansible playbook to automate servers configuration

### Updated the  Name tag on my Jenkins Instance to Jenkins-Ansible, and a new repository created named ansible-config-mgt on my Github


* Installed Ansible on my existing Jenkins Server

` sudo apt update `

` sudo apt install ansible `

` ansible --version ` 

![image for ansible version](./images/Project-11-image-1-Ansible-version.PNG)


* Created a new Freestyle project called ansible in Jenkins and pointed it to ymy ‘ansible-config-mgt’ repository.

![image free style Ansible](./images/)

* Configure Webhook in GitHub and set webhook to trigger ansible build.

![image for webhook](./images/Project-11-image-2-webhook-config.PNG)

* Configured a Post-build job to save all (**) files, like you did it in Project 9.

![image for postbuild job](./images/Project-11-image-3-configured-postbuild.PNG)

* Made some changes in README.MD file in master branch to test if the builds starts automatically and Jenkins saves the files (build artifacts) in the following folder ls /var/lib/jenkins/jobs/ansible/builds/2/archive/


![iamge for tested post build in jenkins](./images/Project-11-image-3a-tested-postbuild-job.PNG)

![image ls /var/lib/jenkins/jobs/ansible/builds/2/archive/](./images/Project-11-image-3ab-tested-postbuild-job-var-lib.PNG)


### Step 2 – Prepared development environment using Visual Studio Code

*  VSC configured and connected my newly created GitHub repository.

* Cloned down your ansible-config-mgt repo to your Jenkins-Ansible instance

`  git clone git@github.com:babalola1234/ansible-config-mgt.git ` 

![image of gir clone above](./images/)

### BEGIN ANSIBLE DEVELOPMENT
* In my ansible-config-mgt GitHub repository, created a new branch called feature/prj-101-ansible.

![image of new branch in github](./images/Project-11-image-4-new-branch-created.PNG)


* Checked out my newly created feature branch to my local machine.

![image for checkout codes](./images/Project-11-image-4-git-checkout-feature.PNG)

* Created a directory named inventory, and touched 4 files as follows dev.yml, staging.yml, uat.yml, and prod.yml respectively.

![image for yml files above](./images/Project-11-image-4d-inventory-stage-uat-prod-dev.PNG)

* Created another dir named playbooks, in it I touched a file called common.yml

![image for pplaybook dir](./images/Project-11-image-4a-playbooks-inventory.PNG)


### Step 4 – Set up an Ansible Inventory

* installed ssh-agent on my jenkins-Ansible server

` ssh-add `

* Confirmed  the key has been added with the command below,

` ssh-add -l `

![image of new key added](./images/Project-11-image-5b-keys-added-to-jenkins-ansible.PNG)


* ssh into Jenkins-Ansible server using ssh-agent

` ssh -A ubuntu@3.134.150.221 `

![image of ssh into jenkin-ansible server](./images/Project-11-image-5c-ssh-into-jenkin-ansible-server-after-keys-added.PNG)


* Updated my inventory/dev.yml file with the below 


![image of inventory update](./images/Project-11-image-5-dev-yml.PNG)

### Step 5 – Created a Common Playbook --common.yml and updated with the below codes


![image of commom.yml]

### Step 6 – Updated GITHUB with the latest code from my local machine

` git status `

` git add .  

` git commit -m "code update" `

![image of git git add and push](./images/Project-11-image-5a-git-add-git-push.PNG)

* Created a Pull request (PR)

![image of compare and pull request ](./images/Project-11-image-6-compare-and-pull-request.PNG)

![image of pull request](./images/Project-11-image-6-PR-pull.PNG)

![image of review and merge ](./images/Project-11-image-6a-merged.PNG)

* jenkins did the automation for after the codes were merged

![image of jenkins build](./images/Project-11-image-7-jenkins-ansible-pulled-job.PNG)


![image of lib for the jenkins](./images/Project-11-image-7a-var-lib-build-3.PNG)


### Step 7 – Runing first Ansible test

` cd ansible-config-mgt `

` ansible-playbook -i inventory/dev.yml playbooks/common.yml ` 

![image of ansible first run](./images/Project-11-image-8-ansible-playbook.-one-failed.PNG)

![image of ansible second run ](./images/Project-11-image-9-wireshark-version-on-my-mysql.PNG)

![image of wireshark ](./images/Project-11-image-9-wireshark-version-on-my-mysql.PNG)















