//SCRIPTED.

//DECLARATIVE
pipeline {
	agent any

	//agent { docker { image 'maven:3.6.3'} }
	//agent { docker { image 'node:13.8'} }

	stages {
		stage('Checkout') {
			steps {
				sh "./gradlew --version"
				echo "Build"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}

		stage('Compile') {
			steps {
				sh "./gradlew assembleDebug"
			}
		}
	}
	post {
		always {
			echo "I am awesome. I run always"
		}
		success {
			echo "I run when you are successful"
		}

		failure {
			echo "I run when you fail"
		}
	}
}
