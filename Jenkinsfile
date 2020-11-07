pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Unit Testing') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Sonar Analysis') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.host.url=http://3.83.185.117:9000 -Dsonar.login=68e942a00abb3165be122b820abd1fd9dd7081ba'
            }
        }
    }
}
