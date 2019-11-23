node('maven') {
      stage('Poll') {
       git 'https://github.com/alv1981/simple-java-maven-app.git'
     }
      stage("build & SonarQube analysis") {
             //def scannerLoc = tool 'sonar-scanner1';
              withSonarQubeEnv(credentialsId:'sonar_token',installationName:'sonarqube-server') {
                    
               // sh "${scannerLoc}/bin/sonar-scanner  -Dsonar.host.url=http://10.168.0.11:9000 -Dsonar.projectKey=maven -Dsonar.projectName=maven -Dsonar.sources=. -Dsonar.projectBaseDir=/home/jenkins/workspace/linux_academi/Pipeline_maven"
               sh "${scannerLoc}/bin/sonar-scanner  -Dsonar.projectBaseDir=/home/jenkins/workspace/linux_academi/sonar_test_javascript -Dsonar.sources=. -Dsonar.host.url=http://10.168.0.11:9000 -Dsonar.projectName=maven -Dsonar.projectVersion=1.0 -Dsonar.projectKey=maven "
              }
                
       }
}
       


