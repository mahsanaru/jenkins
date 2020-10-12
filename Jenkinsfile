pipeline {

  agent any
    
  stages {
    
    stage('Checkout Source') {
      steps {
        git 'https://github.com/mahsanaru/jenkins.git'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(kubeconfigId: 'myKubeconfig',
                          configs: 'myweb.yaml')
        }
      }
    }

  }

}
