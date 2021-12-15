pipeline {
    agent any
###################
    stages {
        stage('sonarQualityCheck') {
            agent{ 
	       docker { 
	         image 'openjdk:11'
	    }
         }   

	    steps {
                echo 'validate code..'
		        sh 'mvn sonar:sonar \
  -Dsonar.host.url=http://52.66.247.59:9000 \
  -Dsonar.login=28f447710c54b726adc659d96c8ebcae3decff89'
            }
        }


####################
        stage('Unit Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
####################

        stage('Unit Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
####################

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }

####################

	 stage('Unit Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
###################
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }




    }
}
