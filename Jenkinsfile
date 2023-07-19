

pipeline {
    agent any
    tools {
           maven "maven:3.9.3"
        }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
                
            }
        }
        stage{'My SonarQube Server'} {
            steps {
                sh 'mvn clean package sonar:sonar'
            }
        }
    }
}
