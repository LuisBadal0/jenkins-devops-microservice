//Scripetd
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }

//Declarative
pipeline{
	//agent any
	//agent {docker {image 'maven:3.6.3'}}
	agent {docker {image 'node:20-alpine3.17'}}
	stages{
		stage('Build'){
			steps {
				//sh 'mvn --version'
				sh 'node --version'
				echo "Build"
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