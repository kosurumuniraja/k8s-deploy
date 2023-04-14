pipeline{
  agent any
  stages{
	  stage('sonar quality status'){
	      agent{
	          docker {
	              image 'maven'
		    }
			     }
	
	
	        steps {
	            script {
	               withSonarQubeEnv(credentialsId: 'sonar-cred') {
    
	                sh 'mvn clean install'
					}
				}
			}
		}
	}	
}





pipeline{
    agent any
    environment {
        PATH = "$PATH:/usr/share/maven/bin"
    }
    stages{
       stage('GetCode'){
            steps{
                git 'YOUR CODE-REPO-LINK'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonarqube-7.9.6') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
    }
}
