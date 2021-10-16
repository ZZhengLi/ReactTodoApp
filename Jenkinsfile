pipeline {
    agent {
        docker {
            image 'docker-alpine-python-node:latest'
        }
    }
    environment { 
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Deploy') { 
            steps {
                sh 'npm start'
            }
        }

        stage('Test') {
            steps {
                sh './spec/ui/addItem.spec.js'
            }
        }
        
    }
}