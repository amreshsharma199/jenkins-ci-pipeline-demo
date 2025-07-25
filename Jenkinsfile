pipeline {
    agent { label, 'slavenode' }
    triggers {
        pollSCM('* * * * *')  // Check every minute
    }
    stages {
        stage('Clone') {
            steps {
                sh './clone.sh'
            }
        }
        stage('Build') {
            steps {
                sh './build.sh'
            }
        }
        stage('Test') {
            steps {
                sh './test.sh'
            }
        }
        stage('Deploy') {
            steps {
                sh './deploy.sh'
            }
        }
    }
}
