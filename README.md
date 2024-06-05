# Install Jenkins on EC2 Ubuntu

Login in to EC2 instance using SSH using the below command;

"ssh -i filename.pem ubuntu@PublicIP"
It says permission denied in the below secreenshot since the private key file is unprotected as it contains sensitive information.
To change permissions of the pem file use "chmod 600 filename.pem" 
 
 





Run “sudo su -” to change the user to a root user.
Run “apt update” to update packages.
Whenever you login to an instance try to update the packages so that you are up to date. So that, whenever you download something, you get the latest version of that package.

 
Jenkins requires JRE which is Java Runtime Environment.
So, check if java is already installed by running  “java - -version”
If not install java using the below command;
apt install default-jre
 

 
# Install Jenkins
https://www.jenkins.io/doc/book/installing/linux/
Refer the above link for the Jenkins installation command for your respective Operating system, Ubuntu in this case.
 
To check if the Jenkins server is up and running, run the below command;
"systemctl status Jenkins" 
Exit the screen using ctrl+z.
By default Jenkins run on port 8080 – Make sure you provide inbound rules for 8080 for your EC2 instance.
 







Open the web browser, access the Jenkins server using http://PublicIP:8080
If it doesn’t work re-check the inbound rule in security settings in the EC2 instance.
 
Run “cat /var/lib/jenkins/secrets/initialAdminPassword” to locate the administrator password.

 











Install suggested or select the plugins to be installed. Used “suggested plugins” option in this case.
 
It takes few minutes for the plugins to install.
 
Provide credentials or skip and continue as admin.
 
Setup instance configuration. Confirm the address to be used for this server since this will be a preferred address for the Jenkins installation.
 


Setup is ready and we can start using the Jenkins now.
 




![image](https://github.com/dhawanmanik84/Install-Jenkins-on-EC2Ubuntu/assets/115876015/37394690-3b6f-4dc5-a54b-2411aaa27606)
