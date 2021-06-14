
pipeline {
   agent any
    stages {
        stage('Git Checkout') {
             steps {
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'a54100fa-6ef6-4a39-895a-d8f271e0d13a', url: 'git@github.com:Intransigense/ems-system.git']]])
                }
            }
        stage('Code Build'){
           steps {
              
              sh "docker -v"
              sh "npm install --global yarn"
              sh "npm install -g @angular/cli@10.2.3"
              sh "npm install -g pkg"
              sh "mvn clean install -DskipTests -Dlicense.skip=true -Ddockerfile.skip=false"
              
          }
       }
    }
}
       
