node('linkdev'){
stage('change to the project') {
sh "cd /root/project/Drupal_project/src"
}
stage('pull the latest code ') {
sh "git pull https://github.com/amribrahim/Drupal_project.git"
}
stage('build the project') {
sh "composer install"
}
stage('Clearing drush caches.') {
sh "drush cache-clear drush"
}

  
}
