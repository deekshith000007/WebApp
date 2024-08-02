Adding a GitHub Webhook for Jenkins Integration
```
1. Go to GitHub and navigate to your repository: deekshith000007/WebApp.
2. Go to Settings.
3. Under Code and automation, select Webhooks.
4. Click Add webhook.
5. Fill in the following details:
    *Payload URL: http://jenkins-Server-public-ipaddress:8080/github-webhook/
    *Content type: application/json
    *Secret: (Optional, if you want to add a secret for security)
    *SSL verification: By default, SSL certificates are verified. To disable (not recommended), uncheck Enable SSL verification.
6. Choose which events you want to trigger the webhook:
    *Just the push event.
    *Send me everything.
    *Let me select individual events.
7. Ensure the webhook is active.
8. Click Add webhook to save your changes.
```
Configuring System Settings in Jenkins: Email Notification and Publish Over SSH
```
1. Email Notification Configuration:
   *Go to Manage Jenkins.
   *Select Configure System.
   *Scroll down to E-mail Notification:
      ->SMTP server: smtp.gmail.com 
      ->Default user e-mail suffix: @gmail.com
   *Click on Advanced:
   *Use SMTP Authentication: Check this box.
      ->User Name: deekshith000007@gmail.com
      ->Password: Enter your email password.
      ->Use SSL: Check this box.
      ->SMTP Port: 465
      ->Reply-To Address: noreply@gmail.com
      ->Use TLS: (Ensure this is checked or configure as needed.)

2. Publish Over SSH Configuration:
   *Scroll down to Publish over SSH:
      ->SSH Server:
        Name: dockerhost
        Hostname: 172.31.30.5 (Private IP of Docker machine)
        Username: dockeradmin
        Remote Directory: /opt/tomcat
      ->Use password authentication, or use a different key:
        Passphrase / Password: Enter your Docker user password.
   *Click Test Connection to ensure it is successful.
   *Click Apply and then Save to confirm the changes.
```
