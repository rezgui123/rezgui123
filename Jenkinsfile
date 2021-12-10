 pipeline{

 agent any
    triggers {
      pollSCM '* * * * *'
    }
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
	
 stage('Checkout Source') {
   steps {
        git branch: 'main', credentialsId: 'b3b770a5-6304-4c16-8a36-55c6214b2707', url: 'https://github.com/rezgui123/rezgui123.git'
      }
    }
	
    stage('Deploy App to Kubernetes') { 
	    
       //    when { branch "main" }
                       steps {
          
			        withCredentials([file(credentialsId: 'mykubeconfig', variable: 'KUBECONFIG')]) {
                                  sh 'kubectl apply -f nginx.yml'
					echo '${BUILD_NUMBER}'

                              }
                            }
                                      }
 }
 }
