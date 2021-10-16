pipeline {
    agent {
        image 'node:13-alpine'
    }
    environment {
        npm_config_cache = 'npm-cache'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Deploy') { 
            steps {
                sh 'expo-cli start'
            }
        }

        stage('Test') {
            steps {
                sh './spec/ui/addItem.spec.js'
            }
        }
        
    }
}