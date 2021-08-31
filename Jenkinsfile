currentBuild.displayName = "Nexus-Upload"
pipeline{
    agent any
    
    stages{
        
        
        
        stage("Maven Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Upload war to Nexus"){
            steps{
                nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'nexus-pipeline',
                        classifier: '', 
                        file: 'target/nexu-pipeline-3.0.0.war', 
                        type: 'war'
                        ]
                    ], 
                    credentialsId: '64a6c3a5-7874-4ce5-aca1-36aad8abaf5e', 
                    groupId: 'nexus', 
                    nexusUrl: '172.31.15.19:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'Jenkins', 
                    version: '3.0.0'
            }
        }
    }
}
