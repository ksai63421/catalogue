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
         stage('SonarScan') {
             steps {
                sh 'ls -l'
                sh 'sonar-scanner'
            }
        }
    }
}
    
