pipeline {
    agent {label 'maven'}
        
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage("build & SonarQube analysis") {
            steps {
              withSonarQubeEnv('sonarqube-server') {
                sh 'mvn -e org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
              }
            }
          }
       
        }
    }

