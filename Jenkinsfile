node('maven') {
      stage('Poll') {
       git 'https://github.com/alv1981/simple-java-maven-app.git'
     }
      stage("build & SonarQube analysis") {
              withSonarQubeEnv('sonarqube-server') {
                    
                 sh 'mvn clean package sonar:sonar -Dsonar.projectName=maven -Dsonar.projectKey=maven' 
                 //sh 'mvn  org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar -Dsonar.projectName=maven -Dsonar.projectKey=maven -Dsonar.projectVersion=$BUILD_NUMBER';  
             }
            
     }
       
}

