pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                 sh script: 'mvn clean package'
            }
        }
        stage('Upload War To Nexus'){
            steps{
               nexusArtifactUploader artifacts: [
                   [artifactId: 'simple-app',
                    classifier: '', 
                    file: 'target/simple-app-3.0.0-SNAPSHOT.war', 
                    type: 'war']
                    ], 
                    credentialsId: '38323a4e-be61-46f8-906f-04b3418f3c89', 
                    groupId: 'in.javahome', 
                    nexusUrl: '3.238.29.93:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'simpleapp-release', 
                    version: '3.0.0-SNAPSHOT'
            }
        }
    }
}
