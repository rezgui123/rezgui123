pipline {
  
agent any
  
   stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/rezgui123/rezgui123.git'
      }
    }
 stage('deploy kube app') {
            steps {
                    script{
kubernetesDeploy(configs: "nginx.yml", kubeconfigId: "mykubeconfig")
               }            }
    }
}
}
