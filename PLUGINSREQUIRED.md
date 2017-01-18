DO INITIAL JENKINS SETUP THROUGH KITEMATIC (DOCKER TOOLBOX)
    DOWNLOAD AND INSTALL KITEMATIC (DOCKER TOOLBOX DOWNLOAD)
    CREATE LOCAL FOLDER to map KITEMATIC JENKINS to
        e.g. ~/Downloads/Installed/repositories/dockerjenkins_volatile
    IF IT ALREADY EXISTS AND IT'S OLD, THEN CLEAN IT OUT (DELTE ALL)'
    MAP IT
        KITEMATIC=>jenkins:latest=>Settings=>Volumes
        DOCKER FOLDER:/var/jenkins_home LOCAL FOLDER: ~/Downloads/Installed/repositories/dockerjenkins_volatile
    START JENKINS
    CREATE FIRST ADMIN USER
        user: sk8creteordie
        password: Sk8Omlb
    PLUGINS
        Email Ext
        github
        nodejs
        publish over ssh
        rebuilder
    JENKINS INSTALL MANAGE PLUGINS 
        thinBackup plugin
    RESTART
    MANAGE JENKINS=>THINBACKUP=>SETTINGS=>BACKUPDIRECTORY=>/var/jenkins_home
    RESTART
    COPY A BACKUP FROM dockerjenkins (git CLONE https://github.com/jimarasim/dockerjenkins) TO LOCAL FOLDER FOR DOCKER FOLDER
    RESTORE THE BACKUP (IT WON'T TAKE EFFECT TILL YOU RESTART KITEMATIC)
        CHECK RESTORE BUILD NUMBERS
        CHECK RESTORE PLUGINS
    RESTART jenkins:latest IN KITEMATIC

RESTORE A BACKUP FROM dockerjenkins GITHUB REPOSITORY
    NEXT TIME: Check restore plugins when restoring from thinbackup
    THINBACKUP => SETTINGS => BACKUP DIRECTORY => MAP dockerjenkins TO A KITEMATIC CONTAINER FOLDER
        git CLONE https://github.com/jimarasim/dockerjenkins
        CREATE LOCAL FOLDER to map KITEMATIC JENKINS to
            e.g. ~/Downloads/Installed/repositories/dockerjenkins_volatile
        if it already exists, and it's old (e.g. old .war file)'
            stop JENKINS in KITEMATIC
            clean it out (delete all if jenkins.war files are different)
                        restart jenkins
        
    restore thin backup if need be
    KITEMATIC=>CONTAINER=>JENKINS=>SETTINGS=>VOLUMES=>/var/jenkins_home



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


