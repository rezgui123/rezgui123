pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('rezguimed')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t rezguimed/nodeapp:latest .'
			}
		}

	

		stage('Push') {

			steps {
				sh 'docker push rezguimed/nodeapp:latest'
			}
		}
	}

	}
