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
                sh "unit testing is done here"

            }
        }
    }
}
    
