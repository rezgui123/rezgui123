pipeline {

  agent any

  stages {


    stage('Deploy App') {
      steps {
      //    kubernetesDeploy(configs: "nginx.yml", kubeconfigId: "mykubeconfig", enableConfigSubstitution: true)
          sh "kubectl  apply -f nginx.yml"
               
                }
    }

  }

}
