pipeline {
    agent any

    stages {
        

        
        stage('sonarQualityCheck') {
     

	    steps {
            script {
                withSonarQubeEnv('sonar-server') {
                    echo 'validatining code..'
                    sh 'mvn clean sonar:sonar'
                  
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



        stage('Nexus Release') {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'WebAppCal', classifier: '', file: 'JavaWebCalculator/target/WebAppCal-0.0.2.war', type: 'war']], credentialsId: 'nexus', groupId: 'com.web.cal', nexusUrl: '172.31.44.35:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-releases', version: '1.3.2'
		
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
