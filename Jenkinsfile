 pipeline{

	agent any



	stages{


               stage('Deploy App to Kubernetes') {     
                      steps {
                           container('test') {
                                   withCredentials([file(credentialsId: 'mykubeconfig', variable: 'KUBECONFIG')]) {
                                   sh 'kubectl apply -f nginx.yml'
          }
        }
      }
    }
  }
	}
