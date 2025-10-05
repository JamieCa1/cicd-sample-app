pipeline {
    agent any
    triggers {
        pollSCM('H/30 * * * *')
    }
    stages {
        stage('Build') {
            steps {
                build 'BuildSampleApp'
            }
        }
        stage('Results') {
            steps {
                build 'TestSampleApp'
            }
        }
    }
}