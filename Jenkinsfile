pipeline {
    agent {
        docker {
            image 'python:3.5.1'
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