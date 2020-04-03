node('linkdev'){
stage('change to the project') {
sh "cd /root/project/Drupal_project"
}
stage('pull the latest code ') {
sh "ls -al"
}
stage('pull the latest code ') {
sh "git pull"
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
