pipeline {
   agent any
   tools {
        maven 'maven 3.9.3'
   }
   stages {
	stage('Code Checkout') {	
	  steps {
		  checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/Vicky050890/Demo-JenkinsPipeline']])
	  }
        }
        stage('Build') {
	  steps {
		bat "mvn clean compile" 
	  }
	}
	stage('Unit Test') {
	  steps {
		bat "mvn clean test"
	  }
	}
   }
}


	
