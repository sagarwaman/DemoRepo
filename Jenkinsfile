pipeline {
	agent any 
	
	
	stages{
		stage('Checkout'){
			steps {
				git branch: 'master', url: 'https://github.com/sagarwaman/DemoRepo.git'
			}
		}
		
		stage('Build'){
			steps {
            echo 'Running Maven clean install....'
            bat 'mvn clean install'
			}
		}
		
		stage('Test'){
			steps {
            echo 'Publishing junit test result'
            bat 'mvn test'
            junit '**/target/surefire-reports/*xml'
			}
		}
	}
}