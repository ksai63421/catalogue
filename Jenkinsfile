pipeline {
    agent { node { label 'agent-1' } }
    stages {
        stage('Install dependencies') {
             steps {
                sh 'npm install'
             }
        }
        stage('Unit test') {
             steps {
                echo "unit testing is done here"

            }
        }
        //sonar-scanner command expects sonar-project.properties should be available
        //  stage('Sonar Scan') {
        //      steps {
        //         sh 'sonar-scanner'
        //     }
        // }
        stage('Build') {
             steps {
                sh 'pwd'
                sh 'ls -ltr'
                sh 'zip -r catalogue.zip ./* --exclude=.git --exclude=.zip'

            }
        }
        stage('Publish Artifact') {
             steps {
                nexusArtifactUploader(
        nexusVersion: 'nexus3',
        protocol: 'http',
        nexusUrl: '54.224.110.82:8081/',
        groupId: 'com.roboshop',
        version: '1.0.1',
        repository: 'catalogue',
        credentialsId: 'nexus-auth',
        artifacts: [
            [artifactId: 'catalogue',
             classifier: '',
             file: 'catalogue.zip',
             type: 'zip']
        ]
     )

    }
}
   
         stage('Deploy') {
             steps {
                echo "Deployment"
            }
        }
        
    }
    post{
        always{
            echo "cleaning up the workspace"
             deleteDir()
        }
    }
}


    
