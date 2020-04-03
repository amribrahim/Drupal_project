node('linkdev'){
stage('pull the latest code ') {
 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-user', url: 'https://github.com/amribrahim/Drupal_project.git']]])
}
stage('deploy changes ') {
 sh """ 
    #!/bin/bash
    cd /root/project/Drupal_project
    git pull
    ls -l
    composer install
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



 
