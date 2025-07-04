pipeline {
    agent any
    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "Whiteout docker"
                    ls -la
                    touch container-no.txt
                '''
            }
        }
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:22.17.0-alpine3.22'
                    reuseNode true
            }
        }
            steps {
                sh '''
                    echo "With docker"
                    ls -la
                    touch container-yes.txt
                '''
            }
        }
    }
}
