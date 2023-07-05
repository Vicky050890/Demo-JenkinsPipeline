pipeline {
   agent any   
   stages {
	stage('Code Checkout') {	
	  steps {
		  checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/Vicky050890/Demo-JenkinsPipeline']])
	  }
        }
        stage('Build') {
	  steps {
		sh 'mvn -Dmaven.test.failure.ignore=true install' 
	  }
	}
   }		  
}


	
