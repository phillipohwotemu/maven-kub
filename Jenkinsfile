


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
    freeStyleJob('NexusArtifactUploaderJob') {
        steps {
          nexusArtifactUploader {
            nexusVersion('nexus2')
            protocol('http')
            nexusUrl('http://54.145.126.153:8081/')
            groupId('sp.sd')
            version('2.4')
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
