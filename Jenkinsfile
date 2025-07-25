pipeline {
    agent { label 'jenkinsslave' }
    triggers {
        pollSCM('* * * * *')  // Check every minute
    }
    stages {
        stage('Clone') {
            steps {
                sh 'chmod +x clone.sh build.sh test.sh deploy.sh'
                sh './clone.sh'
                echo 'auto run ho raha hai polls scm se detect karke'
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
