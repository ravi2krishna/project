pipeline {
    agent any

    stages {
        stage('Testing') {
            steps {
                echo 'Building..'
                sh 'mvn test'
            }
        }
        stage('Sonar') {
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
