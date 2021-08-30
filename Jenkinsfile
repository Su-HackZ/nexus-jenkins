pipeline{
    agent any
    
    stages{
        
        // stage("Git Checkout"){
        //     steps{
        //         git branch: 'main', url: 'https://github.com/superuser6/nexus-jenkins'
        //     }
        // }
        
        stage("Maven Build"){
            steps{
                sh script: 'mvn clean package'
            }
        }
        stage("Upload war to Nexus"){
            steps{
                nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'nexus-pipeline',
                        classifier: '', 
                        file: 'target/nexu-pipeline-1.0.0.war', 
                        type: 'war'
                        ]
                    ], 
                    credentialsId: '64a6c3a5-7874-4ce5-aca1-36aad8abaf5e', 
                    groupId: 'in.javahome', 
                    nexusUrl: '172.31.15.19:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'Jenkins', 
                    version: '1.0.0'
            }
        }
    }
}
