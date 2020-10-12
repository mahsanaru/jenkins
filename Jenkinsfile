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
          kubernetesDeploy(kubeconfigId: "myKubeconfig",
                          configs: "myweb.yaml")
        }
      }
    }

  }

}

pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
        stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(kubeconfigId: "myKubeconfig", 
                           configs: "myweb.yaml")
        }
      }
    }
    }
}
