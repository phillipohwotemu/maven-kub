

pipeline {
    agent any
    tools {
           maven "maven:3.9.3"
        }
    stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('My SonarQube Server') {
                sh 'mvn clean package sonar:sonar'
                
            }
        }
        stage{'My SonarQube Server'} {
            steps {
                sh 'mvn clean package sonar:sonar'
            }
        }
    }
}
