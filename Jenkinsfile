pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo '-------------Building-------------'
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..!!!'
            }
        }
        stage('Publish') {
            steps {
                echo 'Publishing..!!!'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..!!!'
            }
        }
    }
}

