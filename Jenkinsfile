pipeline {
	agent any
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage ('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_ID - $BUILD_ID"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
		    }
	    }
		stage ('compile') {
			steps {
				sh "mvn clean compile"
			}
		}
	    stage ('Test') {
			steps {
				sh "mvn Test"
			}
		}
		stage ('Integrattion Test') {
			steps {
				sh "mvn failsafe:integraion-test failsafe:verify"
			}
		}
	}
	post {
		always {
			echo 'I am awesome. I run always'
		}
		success {
			echo 'Irun when you are successful'
		}
		failure {
			echo 'I run when you are fail'
		}
	}
}
 
