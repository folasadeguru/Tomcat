# Tomcat
Install Tomcat 9 on Ubuntu 18.0.4
drpraizedevops July 22, 2020
Tomcat is one of the popular web containers for deploying Java applications. Tomcat is open source.
Click here to learn more about Tomcat. Let's see how to install Tomcat on Ubuntu 18.0.4.

Please follow below steps to install Tomcat 9 on Ubuntu 18.0.4.

Pre-requistes:
Make sure you create EC2 instance first installing Tomcat. Click here to learn how to create EC2.
Also open port 8080 in security firewall rules for EC2 instance in AWS

Tomcat Installation
Tomcat is a web server or web container where java web application can be deployed by developers. You can learn more about by clicking this URL.  Tomcat can be installed by executing below commands:

Update to Latest packages
sudo apt update

Install Tomcat9
sudo apt-get install tomcat9 tomcat9-docs tomcat9-admin -y




Perform below command for setting up tomcat admin app
sudo cp -r /usr/share/tomcat9-admin/* /var/lib/tomcat9/webapps/ -v
Setup an user in tomcat 
Open the tomcat-users.xml file by executing below command
sudo vi /var/lib/tomcat9/conf/tomcat-users.xml

You need to edit the file, click on this link to know how to make changes using Vi editor.
http://www.cidevops.com/2018/03/how-to-make-changes-in-linux-machine.html
We need to add tomcat user and assign to manager-script role.
Scroll down all the way to the end of the file,
Add the below lines in second last line above (above </tomcat-users>)

<role rolename="manager-script"/>
<user username="tomcat" password="password" roles="manager-script"/>




Now restart tomcat to take the changes in effect
sudo systemctl restart tomcat9

Verify if tomcat is working fine
sudo systemctl status tomcat9




Now press q for quitting from that window. Now open the browser to access Tomcat, enter
http://change to Ec2_public_dns_name:8080
You should see a page that says.




That's it. You have setup Tomcat successfully!!
