pipeline {
    agent any

    stages {
        stage('Code Validation') {
            steps {
                echo 'Validating & Compiling'
                sh 'mvn validate compile'
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
