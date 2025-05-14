pipeline{
	agent any
	
	tools{
		maven 'Maven'
		jdk 'JDK'
	}
	
	stages{
		stage('Checkout'){
			steps{
				git branch : 'master', url : 'https://github.com/Thushardm/PracSelenium.git'
			}
		}
		
		stage('Build'){
			steps{
				sh 'mvn clean install'
			}
		}
		
		stage('Run'){
			steps{
				archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
			}
		}
	}
	
	post{
		success{
			echo 'Success'
		}
		failure{
			echo 'Failed'
		}
	}
}
