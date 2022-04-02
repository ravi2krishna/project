pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                sh 'mvn validate'
            }
        }
        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
