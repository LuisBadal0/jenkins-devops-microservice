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
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerhome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD.ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}

		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Test'){
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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