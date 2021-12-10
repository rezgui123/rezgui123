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
	  stage('Deploy App') {
      steps {
            script {
              try{
                      //    kubernetesDeploy(configs: "nginx.yml", kubeconfigId: "mykubeconfig", enableConfigSubstitution: true)
          sh "sh run.sh"
              }catch (error){
          sh "kubectl  create -f nginx.yml"
              }
                }
    }
    }
  }
	}
