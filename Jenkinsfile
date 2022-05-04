pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
		sh 'cat /etc/os-release123'
                echo 'Building..'
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
