node('linkdev'){
stage('pull the latest code ') {
sh "git clone https://github.com/amribrahim/Drupal_project.git"
}
stage('change to the project') {
sh "cd ./Drupal_project/src "
}  
stage('change to the project') {
sh "cp * -rf  /root/project/Drupal_project/src"
}
stage('change to source ') {
sh "cd /src"
}
stage('build the project') {
sh "composer install"
}
stage('Clearing drush caches.') {
sh "drush cache-clear drush"
}

  
}



