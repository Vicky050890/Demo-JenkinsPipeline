pipeline {
   agent any

   tools {
      maven "Maven3.6"   
   }
   stages {
	stage('Code Checkout'){			
		checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/Vicky050890/Demo-JenkinsPipeline']])
	}
	stage('BuildJob') {
		bat "mvn clean compile"	
	}					
   }		  
}


	
