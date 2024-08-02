Installing Docker
```
sudo yum install docker -y
```
Creating Docker user
```
useradd dockeradmin
passwd dockeradmin
```
Enabling Password Authentication
```
vi /etc/ssh/sshd_config

# To disable tunneled clear text passwords, change to no here!
PasswordAuthentication yes
#PermitEmptyPasswords no
#PasswordAuthentication no
```
Reloading sshd service
```
sudo systemctl sshd reload
```
Granting the dockeradmin user permissions associated with the docker group
```
usermod -aG docker dockeradmin
```
Enabling and Starting the Docker service
```
sudo systemctl enable docker
sudo systemctl start docker
sudo systemctl status docker
```
creating Directory with Tomacat(u can give anyname)
```
 mkdir tomcat
```
Chaning the owenship to dockeradmin
```
chown -R dockeradmin:dockeradmin tomcat
```
Switching to dockeradmin
```
sudo su - dockeradmin
```
Creating Dockerfile
```
cd tomcat

vi Dockerfile 
FROM tomcat:latest
RUN cp -R  /usr/local/tomcat/webapps.dist/*  /usr/local/tomcat/webapps
COPY *.war /usr/local/tomcat/webapps
```
