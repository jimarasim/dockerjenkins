INSTALL THIN BACKUP FIRST THEN RESTORE A BACKUP FROM dockerjenkins GITHUB REPOSITORY
NEXT TIME: Check restore plugins when restoring from thinbackup

USERS
sk8creteordie
Sk8Omlb

jim
jim

PLUGINS
Email Ext
github
nodejs
publish over ssh
rebuilder

CONFIGURATION SETUP
+turn on slave to master security
+JDK - auto, add credentials, carried over from thin backup
+maven - auto, carried over from thin backup
+nodejs - install plugin, settings carried over from thin backup after installation auto
+github plugin - install plugin, settings carried over form thin backup after installation username and email
+thin backup
+extended email notification plugin: install, then settings were there from thin backup; however kept getting errors sending email. the test email button would work in configuration, but the jobs sending email would say jaemzware@hotmail.com was an invalid email address. now saying the address is valid, but send failed. trying to leave default suffix blank
    
    E-mail Notification
ACCOUNTS: suespamnow@stuffedanimalwar.com, jaemzware@gmail.com, jaemzware@hotmail.com
    smtp server: mail.stuffedanimalwar.com, smtp.gmail.com, smtp-mail.outlook.com
    default user email suffix: {BLANK} 
    ,use smtp authentication,
    user name: suespamnow@stuffedanimalwar.com, jaemzware@gmail.com, jaemzware@hotmail.com
    password: 8bigfish, G00G73g00g73, Y0urM0m777
    use ssl: uncheck, check, check
    port: 587, 465, 993
    reply to: suespamnow@stuffedanimalwar.com, jaemzware@gmail.com, jaemzware@hotmail.com

    Extended Email Notification
smtp server: smtp.gmail.com
default user email suffix: @gmail.com
default content type: html
default recipients: jaemzware@hotmail.com
reply to list: jaemzware@gmail.com
default triggers: always
    

+excecutors 10, carried over from thin backup
+global properties JENKINSREPORTSURL: http://jaemzware.com/jenkinsreports
+publish over ssh, install then settings carried over from thin backup, have to re-enter password
    passphrase: SkatePark@3
    ...
    ssh server:
    name: seattlerules
    hostname: seattlerules.com
    username: jimara0
    remote directory: jaemzware.com/jenkinsreports
+rebuilder plugin
+upgrade plugins
+jobs - github credentials were stored, but password had to be re-entered for the global credential
NOTE: Views did not carry over. try another thin backup, 


