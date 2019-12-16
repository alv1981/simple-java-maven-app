pipeline {
   agent any

   stages {
      stage('gitpoll') {
         steps {
            git 'https://github.com/alv1981/simple-java-maven-app.git'
         }
      }
      stage('build') {
         agent {label 'maven'}
         def scannerLoc = tool 'sonar-scanner1';
         steps {            
            withSonarQubeEnv(credentialsId:'sonar_token',installationName:'sonarqube-server') {
              sh 'mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar -Dsonar.projectBaseDir=/home/jenkins/workspace/linux_academi/Pipeline_maven -Dsonar.sources=. -Dsonar.host.url=http://10.168.0.11:9000 -Dsonar.projectName=maven -Dsonar.projectVersion=1.0 -Dsonar.projectKey=maven'   
            }
           }
       } 
      
   }
}
