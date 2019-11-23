node('maven') {
      stage('Poll') {
       git 'https://github.com/alv1981/simple-java-maven-app.git'
     }
      stage("build & SonarQube analysis") {
             def scannerLoc = tool 'sonar-scanner1';
              withSonarQubeEnv('sonarqube-server') {
                    
                sh "${scannerLoc}/bin/sonar-scanner  -Dsonar.host.url=http://10.168.0.11:9000 -Dsonar.projectKey=maven -Dsonar.projectName=maven -Dsonar.sources=. -Dsonar.projectBaseDir=/home/jenkins/workspace/linux_academi/Pipeline_maven"
              }
                
       }
}
       


