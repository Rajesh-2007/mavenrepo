pipeline{
 agent {label'Dev 1'}
triggers {
  pollSCM '* * * * *'
}
stages{
stage('git'){
steps{
checkout([$class: 'GitSCM', branches: [[name: '*/Feature']], extensions: [], userRemoteConfigs: [[credentialsId: '9f3dc9d8-4079-4e42-ad8f-7e7ef66cdfa1', url: 'https://github.com/Rajesh-2007/mavenrepo']]])
}
}
stage('package'){
steps{
sh 'mvn package'
}
}
stage('Sonar'){
steps{
withSonarQubeEnv('Sonar') {
   sh 'mvn sonar:sonar' 
}
}
}
}
}
