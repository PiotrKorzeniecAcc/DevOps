pipeline {
    agent any
    tools {
	maven 'Maven 3.9.6'
	jdk 'jdk8'
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
		    sh 'mvn sonar:sonar'
		    }
	    }
	}
    }
}
