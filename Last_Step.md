Adding Github Webhook
```
go to github
deekshith000007/WebApp
goto Settings ->
below in  the option of Code and automation -> Webhook
add Webhook
Payload URL * http://jenkins-Server-public-ipaddress:8080//github-webhook/
Content type * application/json
Secret
SSL verification
 By default, we verify SSL certificates when delivering payloads.
*Enable SSL verification*  Disable (not recommended)

Which events would you like to trigger this webhook?
Just the push event.
* Send me everything.*
Let me select individual events.

*active*
Add Webhook
```
Managing System in the Jenkins
```
Goto manage jenkins-> System Configuration -> system
-----------------------------------------------------
-> E-mail Notification
SMTP server : smtp.gmail.com
Default user e-mail suffix : @gmail.com

Advanced
*Use SMTP Authentication*
*Use SSL*
Use TLS

Use SMTP Authentication
User Name : deekshith000007@gmail.com
Password  : password

Use SSL
SMTP : 465
Reply-To Address: noreply@gmail.com

-----------------------------------------------------
-> Publish over SSH
SSH Server

Hostname : Dockerhost
Username : 172.31.30.5(Privateip Docker machine)
Remote Directory : /opt/tomcat


ssh server
Name dockerhost
Hostname 172.31.30.5
Username dockeradmin
Remote Directory /opt/tomcat

Use password authentication, or use a different key
Passphrase / Password : Enter your dockeruser password

testconnection->success
apply save
------------------------------------------------------------
```
