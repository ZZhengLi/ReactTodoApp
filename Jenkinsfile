pipeline {
    agent {
        docker {
            image 'node:8.12.0'
        }
    }
    environment { 
        CI = 'true'
        HOME = '.'
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