node('maven') {
      stage('Poll') {
       git 'https://github.com/alv1981/simple-java-maven-app.git'
     }
      stage("build & SonarQube analysis") {
             def scannerLoc = tool 'sonnar-scanner1';
              withSonarQubeEnv('sonarqube-server') {
                    
                 sh "${scannerLoc}/bin/sonar-runner  
                 //sh 'mvn  org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar -Dsonar.projectName=maven -Dsonar.projectKey=maven -Dsonar.projectVersion=$BUILD_NUMBER';  
             }
            
     }
       
}

