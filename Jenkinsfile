 pipeline{

 agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('rezguimed')
	}

	stages{

		stage('Build') {

			steps {
				sh 'docker build -t rezguimed/nodeapp:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}	

		stage('Push') {

			steps {
				sh 'docker push rezguimed/nodeapp:latest'
			}
		}

               stage('Deploy App to Kubernetes') {     
                      steps {
                          // container('test') {
                                   withCredentials([file(credentialsId: 'mykubeconfig', variable: 'KUBECONFIG')]) {
                                   sh 'kubectl apply -f nginx.yml'
          //}
        }
      }
    }
  }
	}
