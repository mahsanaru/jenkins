pipeline {


  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/mahsanaru/jenkins.git'
      }
    }

    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
