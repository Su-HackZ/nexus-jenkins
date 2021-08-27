pipeline{
    agent any
    tools {
        maven 'maven'
    }
    stages{
        stage('Build'){
            steps{
                sh script: 'mvn clean package'
            }
        }
        stage('Upload war to Nexus'){
            steps{
                nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'nexus pipeline',
                        classifier: '', 
                        file: 'target/nexus pipeline-1.0.0.war', 
                        type: 'war'
                        ]
                    ], 
                    credentialsId: '64a6c3a5-7874-4ce5-aca1-36aad8abaf5e', 
                    groupId: 'in.javahome', 
                    nexusUrl: '172.31.15.19:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'http://3.142.43.121:8081/repository/Jenkins', 
                    version: '1.0.0'
            }
        }
    }
}