pipeline {
    agent any

    stages {
        stage('Vaidation') {
            steps {
                echo 'Validate Project..'
		sh 'mvn validate'
		sh 'mvn compile'
            }
        }
        stage('UnitTest') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
        stage('SonarAnalysis') {
            steps {
                echo 'Sonar Analysis....'
		sh 'mvn sonar:sonar -Dsonar.host.url=http://54.177.202.113:9000 -Dsonar.login=79f63dcd396aa64e0a4ed1f603097bc9ce2b93b1'
            }
        }
    }
}
