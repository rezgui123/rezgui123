pipeline {

  agent any

  stages {


    stage('Deploy App') {
      steps {
            script {
              try{
                      //    kubernetesDeploy(configs: "nginx.yml", kubeconfigId: "mykubeconfig", enableConfigSubstitution: true)
          sh "kubectl  apply -f nginx.yml"
              }catch (error){
          sh "kubectl  create -f nginx.yml"
              }
                }
    }

  }

}
