node('linkdev'){
stage('pull the latest code ') {
// checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-user', url: 'https://github.com/amribrahim/Drupal_project.git']]])
}
stage('deploy changes ') {
 sh """ 
    #!/bin/bash
    cd /root/project/Drupal_project
    git pull
    ls -l
    cd src
    composer install
    """
}  
 
 stage('Post Deployment stage '){
   sh """ 
    #!/bin/bash
    cd /root/project/Drupal_project
    bash post-deployment.sh
    """
 }
 
  stage('backup the source code and database'){
   sh """ 
    #!/bin/bash
    cd /root/project/Drupal_project
    bash backup.sh
    """
 }
/*
 stage('copy files to src') {
sh label: '', script: 'cp * -rf  /root/project/Drupal_project/src'
}
stage('change to the project') {
sh label: '', script: 'cd /root/project/Drupal_project/src '
}
stage('build the project') {
sh "composer install"
}
*/
  
}



 
