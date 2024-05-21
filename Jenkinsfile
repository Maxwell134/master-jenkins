pipeline {
    agent any

    stages {
        stage('Create Docker image') {
            steps {
                sh 'docker build -t test:v1 .'
            }
        }
        stage('Delete old container') {
            steps {
                sh 'docker rm -f nginx'
            }
        }

        stage('Create a container') {
            steps {
                sh 'docker run -d --name nginx -p 82:80 test:v1'
            }
        }
        
    }
}
