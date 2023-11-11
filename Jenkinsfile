pipeline {
	agent {
		docker {
			image 'composer:lts'
		}
	}
	stages {
		stage('ECHO ECHO') {
			steps {
				echo "docker ps"
			}
		}
		stage('Checkout SCM') {
			steps {
				checkout scm
			}
		}
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}