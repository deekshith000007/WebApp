Jenkins  download 
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
Install Git
```
yum install git -y
```
Configuring Jenkins in the Browser
```
Jenkins-Server-IPaddress:8080
```
Retrieving the Initial Admin Password for Jenkins
```
cat /var/lib/jenkins/secrets/initialAdminPassword
```
Installing and Setting up the Apache Maven
```
official website: https://dlcdn.apache.org/maven/maven-3/3.9.8/binaries/apache-maven-3.9.8-bin.tar.gz

wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz

 tar -xvzf apache-maven-3.9.6-bin.tar.gz

 mv apache-maven-3.9.6 maven(Renaming. You can give any name here)
```
Setting up the currect java version to the Jenkins
```
amazon-linux-extras install java-openjdk11
```
Setup for environment variables
```
cd
vi .bash_profile
M2_HOME=/opt/maven
M2=/opt/maven/bin
JAVA_HOME=/usr/lib/jvm/java-11-openjdk-11.0.22.0.7-1.amzn2.0.1.x86_64
PATH=$PATH:$HOME/bin:$M2_HOME:$M2:$JAVA_HOME
 ```
Update and verify the environment variables 
```
source .bash_profile
echo $PATH
```
Installing Essential Plugins in Jenkins: GitHub, Maven Integration, and Publish Over SSH
```
1. Open the Jenkins webpage.
2. Navigate to Manage Jenkins.
3. Select Manage Plugins under System Configuration.
4. Go to the Available tab.
5. Search for the following plugins:
   GitHub
   Maven Integration
   Publish Over SSH
```
Configuring Necessary Tools in Jenkins: JDK and Maven
```
1. Navigate to Manage Jenkins.
2. Select Global Tool Configuration under System Configuration.
3. Under JDK installations:
         Click Add JDK.
         Set Name to Java-11 (or any preferred name).
         Set JAVA_HOME to /usr/lib/jvm/java-11-openjdk-11.0.22.0.7-1.amzn2.0.1.x86_64.
5.Under Maven installations:
         Click Add Maven.
         Set Name to maven (or any preferred name).
         Set MAVEN_HOME to /opt/maven.
```



