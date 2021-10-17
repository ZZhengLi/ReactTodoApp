pipeline {
    agent { 
        docker { 
            image 'sitapati/docker-alpine-python-node:latest'
            args '-p 3000:3000'
        }
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
                sh 'npm start &'
				input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'chmod +x ./kill.sh'
            }
        }
        stage('Test') {
            steps {
                sh 'npm start &'
                sh '/spec/ui/addItem.spec.js'
                sh '/spec/ui/taskAdded.spec.js'
                sh '/spec/ui/taskChecked.spec.js'
                sh '/spec/ui/taskDelete.spec.js'
            }
        }
    }
}
