pipeline {
    agent any
    
    stages {
        stage('Pull Repository') {
            steps {
                // Checkout the repository
                checkout scm
            }
        }
	stage('SonarQube') {
		steps {
			withSonarQubeEnv(installationName: 'sonarqube-server') {
				sh 'mvn sonar:sonar'
			}
		}
	}
    }
}
