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
        stage('Sonar Analysis') {
            steps {
		sh 'mvn sonar:sonar  -Dsonar.host.url=http://18.212.75.122:9000 -Dsonar.login=e3117fe7ce4e28419ee234c75acc776207c73b95'
            }
        }
    }
}

