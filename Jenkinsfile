pipeline {
	agent { label 'JenkinsAgent' }
	tools{
		jdk 'JDK21'
		maven 'Maven3'
	}
	stages {
		stage("Cleanup Workspace"){
			steps{
				echo "starting Cleaning workspace"
				cleanWS()
				echo "Workspace cleaned"
			}
		}
		stage("Checkout From SCM"){
			steps{
				git branch: 'main', credentialsId: 'github', url: 'https://github.com/vaishnavi0305/register-app'
			}
		}
		stage("Build Application"){
			steps{
				sh "mvn clean package"
			}
		}
		stage("Test Application"){
			steps{
				sh "mvn test"
			}
		}
		
	}
	
}
