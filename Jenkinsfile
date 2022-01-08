pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                echo 'Validating..'
		sh 'mvn validate'
            }
        }
        stage('Unit Testing') {
            steps {
                echo 'Unit Testing..'
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
