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
				sh 'mvn exec:java -Dexec.mainClass=com.example.App'
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
