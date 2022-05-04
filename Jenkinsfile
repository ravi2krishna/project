pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
		sh 'cat /etc/os-release'
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
