pipeline {
    agent any
    environment{
        VERSION = "${env.BUILD_ID}"
    }

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

        stage('Build war file') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Nexus Release') {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'WebAppCal', classifier: '', file: 'target/WebAppCal-1.3.2.war', type: 'war']], credentialsId: 'nexus', groupId: 'com.web.cal', nexusUrl: '172.31.44.35:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-releases', version: '1.3.2'
		
            }
        }

        stage('docker build and docker push') {
            steps {
                script{
                    withCredentials([string(credentialsId: 'registry_pw', variable: 'registry_password')]) {
                       sh '''
                       docker build -t 172.31.44.35:8082/webappcal:${VERSION} .
                       docker tag 172.31.44.35:8082/webappcal:${VERSION} 172.31.44.35:8082/webappcal:latest
                       docker login -u admin -p $registry_password 172.31.44.35:8082
                       docker push 172.31.44.35:8082/webappcal:${VERSION}
                       docker rmi 172.31.44.35:8082/webappcal:${VERSION}
                       '''
                    }
                   
                }
            }
        }
	    stage('Manual approval') {
            steps {
                timeout(10) {
                        mail bcc: '', body: "Please click on the below link to review and approve deployment http://13.233.214.250:8080/job/pipeline_test/${env.BUILD_NUMBER}/console ", cc: '', from: '', replyTo: '', subject: 'Need approval to deploy', to: 'muqeeth.23@gmail.com'
                        input id: 'Deploygate', message: "Deploy ${env.JOB_NAME}?", ok: 'deploy' 
                        }
            }
        }

        stage('Deploy with approval') {
            steps {
                script{
                    withCredentials([kubeconfigFile(credentialsId: '7f2f53d9-632b-46e9-a7fc-ab7349cdf007', variable: 'KUBECONFIG')]) {    
                        dir('k8smanifest') {
                            kubectl apply -f registrysecret.yml
                            kubectl apply -f deployment.yml
                            kubectl apply -f service.yml
                        }                    
                    
                    }
                }
                
            }
        }

    }
    post {
		always {
			mail bcc: '', body: "<br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "${currentBuild.result} CI: Project name -> ${env.JOB_NAME}", to: "muqeeth.23@gmail.com";  
		}
	}
}
