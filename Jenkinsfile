pipeline {

  agent any

  stages {


    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yml", kubeconfigId: "mykubeconfig", enableConfigSubstitution: true)
        }
      }
    }

  }

}
