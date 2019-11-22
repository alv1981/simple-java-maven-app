node('maven') {
      stage('Poll') {
       git url:https://github.com/alv1981/simple-java-maven-app.git
     }
      stage("build & SonarQube analysis") {
              //def scannerLoc = tool 'sonar-scanner';
              withSonarQubeEnv('sonarqube-server') {
                 //  sh "${scannerLoc}/sonar-scanner"
                   sh 'mvn -e org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
             }
            
     }
       
}

