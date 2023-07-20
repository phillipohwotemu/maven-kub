


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
        stage('code review') {
            steps {
                withSonarQubeEnv('sonar-sever-8.9.2'){
                     sh 'mvn clean package sonar:sonar'
                }
            }
        }
         stage('NexusArtifactUploaderJob') {

        steps {

          nexusArtifactUploader {

            nexusVersion('NEXUS3')

            protocol('http')

            nexusUrl('http://54.145.126.153:8081/')

            groupId('sp.sd')

            version('0.0.1-SNAPSHOT')

            repository('NexusArtifactUploader')

            credentialsId('Nexus-credentials')

            artifact {

                artifactId('oductcatalogue')

                type('jar')

                classifier('debug')

                file('oductcatalogue.jar')

            }

            artifact {

                artifactId('oductcatalogue')

                type('hpi')

                classifier('debug')

                file('oductcatalogue.hpi')

            }

          }

        }

    }




    }
}
