 pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('rezguimed')
	}

	stages{


               stage('Deploy App to Kubernetes') {     
                       steps {
                           container('default') {
                                   withCredentials([file(credentialsId: 'mykubeconfig', variable: 'KUBECONFIG')]) {
         //   sh 'sed -i "s/<TAG>/${BUILD_NUMBER}/" nginx.yml'
                                   sh 'kubectl apply -f nginx.yml'
          }
        }
      }
    }
  }
	}
