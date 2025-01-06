pipeline {
	//agent any
	agent {docker {image 'node:lts-jod'}}
	stages {
		stage ('Build') {
			steps {
				sh 'node --version'
				echo "Build"
		    }
	    }
	    stage ('Test') {
			steps {
				echo "Test"
			}
		}
		stage ('Integrattion Test') {
			steps {
				echo "Integration Test"
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
 
