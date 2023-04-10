pipeline{
  agent any
  stages{
	  stage ('sonar quality status'){
	      agent{
	          docker {
	              image 'maven'
		    }
			     }
	
	
	        steps {
	            script {
	               withSonarQubeEnv(credentialsId: 'sonar-cred') {
    
	                sh 'mvn clean package sonar:sonar'
			}
		    }
		}
	}
   }	
}
