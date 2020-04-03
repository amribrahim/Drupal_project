node('linkdev'){
stage('pull the latest code ') {
sh "git pull https://github.com/amribrahim/Drupal_project.git"
}
stage('change to the project') {
sh "cd ./Drupal_project/src "
}  
stage('change to the project') {
sh "cp * -rf  /root/project/Drupal_project/src"
}
stage('build the project') {
sh "composer install /root/project/Drupal_project/src"
}
  
}



