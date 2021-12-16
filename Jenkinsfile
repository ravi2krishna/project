pipeline {
    agent any

    stages {
        

        
        stage('sonarQualityCheck') {
     

	    steps {
            script {
                withSonarQubeEnv('sonarQube') {
                    echo 'validatining code..'
                    //sh 'mvn clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                    //sh 'mvn sonar:sonar'
                   sh 'mvn sonar:sonar \
  -Dsonar.host.url=http://172.31.4.113:9000 \
  -Dsonar.login=28f447710c54b726adc659d96c8ebcae3decff89'

                }

        
            
              timeout(time: 1, unit: 'HOURS'){
                  def qg = waitForQualityGate()
                  if (qg.status != 'OK'){
                      error "Pipeline aborted due to quality gate failure: ${qg.status}"
                  }
              }
        }
        }
        }


        stage('sonarqualitygate') {
            steps {
                echo 'Testing..'
		
            }
        }


        stage('Unit Test') {
            steps {
                echo 'Testing..'
		
            }
        }


        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }



	 stage('Unit Test1') {
            steps {
                echo 'Testing..'
               
            }
        }

        stage('Deploy1') {
            steps {
                echo 'Deploying....'
            }
        }




    }
}
