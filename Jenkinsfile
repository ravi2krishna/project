pipeline {
    agent any

    stages {
        stage('Testing') {
            steps {
                echo 'Validating & Compiling'
                sh 'mvn test'           
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
