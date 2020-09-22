pipeline {
    agent any

    stages {
        stage('Testing') {
            steps {
                echo 'Validating & Compiling'
                sh 'mvn test'           
            }
        }
        stage('Sonar') {
            steps {
                sh 'sleep 5'
                echo 'Testing..'
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sleep 5'
                echo 'Deploying....'
            }
        }
    }
}
