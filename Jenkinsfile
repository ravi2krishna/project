pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'date'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'uname'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
