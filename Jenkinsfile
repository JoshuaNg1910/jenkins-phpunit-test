pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
	stages {
                stage('Checkout SCM') {
                        steps {
                                git 'https://github.com/JoshuaNg1910/jenkins-phpunit-test'
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