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

    }

}