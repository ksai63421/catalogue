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
                sh 'ls -ltr'
                sh 'zip -r ./* --exclude=.git'

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
            echo "cleaning up workspace"
             //deleteDir()
        }
    }
}
    
