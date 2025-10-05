pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Preparation') {
            steps {
                script {
                    sh 'docker stop samplerunning || true'
                    sh 'docker rm samplerunning || true'
                }
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t sampleappimage .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d --name samplerunning -p 8080:80 sampleappimage'
            }
        }
        stage('Results') {
            steps {
                echo 'Deployment completed!'
            }
        }
    }
}