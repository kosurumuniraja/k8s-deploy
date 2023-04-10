pipeline{
  agent any
  stages{
	  stage ('sonar quality check'){
	      agent{
	          docker {
	              image 'maven'
		    }
			     }
	
	
	        steps {
	            script {
	               withSonarQubeEnv(credentialsId: 'sonar-cred')
			    bat “mvn sonar:sonar”
			}
		    }
		}
	}
   }	
}
