node('maven') {         
      stage("build & SonarQube analysis") {
              //def scannerLoc = tool 'sonar-scanner';
              withSonarQubeEnv('sonarqube-server') {
                 //  sh "${scannerLoc}/sonar-scanner"
                   sh 'mvn -e org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
             }
            
     }
       
}

