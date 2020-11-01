pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                sh 'mvn validate compile'
            }
        }
        stage('Unit Testing') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Sonar Analysis') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.host.url=http://3.235.144.43:9000 -Dsonar.login=e2923543dd4eec65fb9908993acdea3c21dc0b2c'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
