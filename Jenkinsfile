//Scripetd
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }

//Declarative
pipeline{
	agent any
	//agent {docker {image 'maven:3.6.3'}}
	//agent {docker {image 'node:20-alpine3.17'}}
	stages{
		stage('Build'){
			steps {
				//sh 'mvn --version'
				//sh 'node --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD.ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Test'){
			steps {
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps {
				echo "Integration Test"
			}
		}
	} 

	post {
		always {
			echo 'Im awesome. I Run Always'
		}
		success {
			echo 'I Run when I succeed'
		}
		failure {
			echo 'I Suck'
		}
		//changed -> stage of the build changes

	}

}