pipeline{
	agent {label 'jenkins-agent'}
	tools{
		jdk 'Java17'
		maven 'Maven3'
	}

	stages{
		stage('Cleaning Workspace'){
			steps{
				cleanWs()
			}
		}

		stage('SCM Checkout'){
			steps{
				git branch: 'main', credentialsId: 'github' , url: 'https://github.com/sourav2128/register-app' 
			}
		}

		stage('Build'){
			steps{
				sh "mvn clean package"
			}
		}

		stage('Test'){
			steps{
				sh "mvn test"
			}
		}
	}
}
