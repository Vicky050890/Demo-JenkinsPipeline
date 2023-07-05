pipeline {
   agent any
   tools {
        maven 'Maven 3.9.3'
        jdk 'jdk8'
   }
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


	
