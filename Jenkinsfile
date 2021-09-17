pipeline {
    agent any

    stages {
        stage('Vaidation') {
            steps {
                echo 'Validate Project..'
		sh 'mvn validate'
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
