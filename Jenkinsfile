pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh '/usr/share/maven/bin/mvn package'
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
