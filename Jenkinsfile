pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                echo 'Validate..'
                sh 'mvn validate'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
