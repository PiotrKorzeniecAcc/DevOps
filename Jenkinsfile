pipeline {
    agent any
    tools {
	maven '3.9.6'
    }
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
		    sh 'mvn clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.10.0.2594:sonar'
		}
	    }
	}
    }
}
