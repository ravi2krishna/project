pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                echo 'Code Validation..'
		sh 'mvn validate'
            }
        }
        stage('UnitTest') {
            steps {
                echo 'Unit Testing..'
		sh 'mvn test'
            }
        }
        stage('SonarAnalysis') {
            steps {
                echo 'Analysis On Bugs....'
		sh 'mvn sonar:sonar -Dsonar.host.url=http://54.177.165.242:9000 -Dsonar.login=c3dce2368b46ba6c41a9a733dfd3849587650aaf'
            }
        }
    }
}
