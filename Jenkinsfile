pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                sh 'uname'
                sh 'cat /etc/os-release'
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Build') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
