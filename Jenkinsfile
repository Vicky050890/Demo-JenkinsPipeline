pipeline {
   agent any

   tools {
      maven "Maven3.6"   
   }
	stage('Code Checkout'){
		println("***Code Checkout stage running for Maven Application***")
		checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/Vicky050890/Demo-JenkinsPipeline']])
	}

	stage('BuildJob') {
		steps {
			script {
				try {
					println("***Build stage running for Maven Application***")
					bat "mvn clean compile"	
				}
				catch(Exception e1) {					
					def testIssue = [fields: [project: [key: 'GUES'],
										summary: 'Maven Build Failed',
										description: 'Maven Build Failed',
										issuetype: [name: 'Bug']]]
					
					response = jiraNewIssue issue: testIssue, site: 'JIRA'					
					echo response.successful.toString()
					echo response.data.toString()
				}
			}
		}
	  }
}

	
