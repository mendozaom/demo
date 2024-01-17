pipeline {
	agent any

	environment {
		mavenHome = tool 'jenkins-maven'
	}

	tools {
		jdk '8'
		jenkins-maven '3.9.6'
	}

	stages {

		stage('Build'){
			steps {
				sh 'mvn clean install -DskipTests'
			}
		}

		stage('Test'){
			steps{
				sh "mvn test"
			}
		}

		stage('Deploy') {
			steps {
			    sh "mvn jar:jar deploy:deploy"
			}
		}
	}
}
