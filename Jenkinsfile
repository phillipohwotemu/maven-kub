node{
    
    stage('Clone repo'){
        git credentialsId: 'powhotemu', url: 'https://github.com/phillipohwotemu/maven-web-app.git'
    }
    
    stage('Maven Build'){
        def mavenHome = tool name: "Maven-3.9.2", type: "maven"
        def mavenCMD = "${mavenHome}/bin/mvn"
        sh "${mavenCMD} clean package"
    }
