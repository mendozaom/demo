pipeline {
	agent any

	environment {
		mavenHome = tool 'jenkins-maven'
	}

	tools {
		jdk '17'
		maven 'jenkins-maven'
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
			sh "mvn --version"	
			    sh "mvn jar:jar deploy:deploy -X"
			}
		}
	}
}
