## LinK Development TasK
This project consists of the following 
- Docker compose file conisits of four docker images Drublal,Mysql,nginx,jenkins
- Docker file for drupale
- jenkins file for contionus Deployment 
- some helper scripts 
#### the Flow of deployment like the following  

![deployment flow](/flowdigram.jpg)

#### Describtion of jenkins and docker files :
- jenkins file consists of three stage each do specific task
  - first stage to pull the last code and deploy it inside the volume contain the code 
  - second stage to run script for post deployment 
  - third stage to run the script for backups and so on 
  - note i did not add any real command in the post script and backup script as this need more specification 
- Docker compose file contain four services
  - first is nginx image using lastest image and contain volumes to the conf files and html files to bind it 
     with src folder inside the server to easy deploy the code 
  - second Drupal image which is custom image to install all need package need for the project 
    you can find the Docker file inside Docker docker//php-fpm-composer and also volume for src code 
  - third mysql image to with some env variables with random passwords and db name and db user and volume 
    for /var/lib/mysql which hold all mysql data 
  - fourth jenkins image for CI and CD and also volume for jenkins home folder which contain all jobs 
- the Docker file for drubal using the image of php:7.3.6-fpm and run alot of apt comamnd to install required packages 
  and to install get composer but the dush i install it inside the jenkins slave instead of container as we did not need 
  it here and make the workdir /var/www/html for the code to used by nginx 
