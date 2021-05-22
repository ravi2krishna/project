pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                echo 'Validating..'
		sh 'mvn compile'
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
        stage('Sonar Analysis') {
            steps {
                echo 'Analyzing....'
		sh 'mvn sonar:sonar -Dsonar.host.url=http://3.236.212.148:9000 -Dsonar.login=5f0d4c395b8e3ff0d5f26dc31f4876c10423412d'
            }
        }
    }
}
