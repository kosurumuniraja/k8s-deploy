pipeline{
  agent any
  stages{
	  stage('SonarQube analysis') {
    tools {
        jdk "Java 11" // the name you have given the JDK installation in Global Tool Configuration
    }
    environment {
        scannerHome = tool 'SonarQube Scanner' // the name you have given the Sonar Scanner (in Global Tool Configuration)
    }
	steps {
	            script {
			    withSonarQubeEnv(credentialsId: 'sonar-cred') {
			    sh "${scannerHome}/bin/sonar-scanner -X"
			}
		    }
		}
	}
   }	
}
