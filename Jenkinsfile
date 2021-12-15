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
            {scrip {
                withSonarQubeEnv(credentialsId: 'sonarqube') {
                    echo 'validatining code..'
                    sh 'mvn sonar:sonar'

                }

            }
            }
            
              timeout(time: 1, unit: 'HOURS'){
                  def qg = waitForQualityGate()
                  if (qg.status != 'OK'){
                      error "Pipeline aborted due to quality gate failure: ${qg.status}"
                  }
              }
        }
        }


####################
        stage('sonarqualitygate') {
            steps {
                echo 'Testing..'
		#sh 'mvn test'
            }
        }
####################

        stage('Unit Test') {
            steps {
                echo 'Testing..'
		#sh 'mvn test'
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
                #sh 'mvn test'
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
