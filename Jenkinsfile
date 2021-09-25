pipeline {
    agent any

    stages {
        stage('Validate') {
            steps {
                echo 'Code Validation..'
            }
        }
        stage('UnitTest') {
            steps {
                echo 'Unit Testing..'
            }
        }
        stage('SonarAnalysis') {
            steps {
                echo 'Analysis On Bugs....'
            }
        }
    }
}
