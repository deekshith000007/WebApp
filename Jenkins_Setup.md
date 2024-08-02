-> Jenkins  download 
```
#!/bin/bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade -y
# Add required dependencies for the jenkins package
sudo yum install java -y
sudo yum install jenkins -y
sudo systemctl daemon-reload
sudo systemctl enable jenkins
sudo systemctl start jenkins
```
-> Install Git
```
yum install git -y
```
-> Setting up and configuring Jenkins in the browser
```
Jenkins-Server-IPaddress:8080
```
-> In the terminal to get the password of jenkins
```
cat /var/lib/jenkins/secrets/initialAdminPassword
```
Installing and Setting up the Apache Maven
```
https://dlcdn.apache.org/maven/maven-3/3.9.8/binaries/apache-maven-3.9.8-bin.tar.gz
wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz

 tar -xvzf apache-maven-3.9.6-bin.tar.gz

 mv apache-maven-3.9.6 maven(Renaming. You can give any name here)
```
Setting up the version to the Jenkins
```
amazon-linux-extras install java-openjdk11
```
Making the maven as environment variable
```
cd
vi .bash_profile
M2_HOME=/opt/maven
M2=/opt/maven/bin
JAVA_HOME=/usr/lib/jvm/java-11-openjdk-11.0.22.0.7-1.amzn2.0.1.x86_64
PATH=$PATH:$HOME/bin:$M2_HOME:$M2:$JAVA_HOME
 ```
Sourcing the variables
```
source .bash_profile
echo $PATH
```
Downloading the neccassary plugins
```



