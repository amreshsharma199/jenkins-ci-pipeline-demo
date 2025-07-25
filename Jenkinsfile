pipeline {
    agent { label 'jenkinsslave' }
    triggers {
        pollSCM('* * * * *')  // Check every minute
    }
    stages {
        stage('Clone') {
            steps {
                sh chmod +x clone.sh build.sh test.sh deploy.sh
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
