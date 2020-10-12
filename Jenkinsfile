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
          kubernetesDeploy configs: 'myweb.yaml', kubeConfig: [path: ''], kubeconfigId: 'myKubeconfig', secretName: '', ssh: [sshCredentialsId: '*', sshServer: ''], textCredentials: [certificateAuthorityData: '', clientCertificateData: '', clientKeyData: '', serverUrl: 'https://']
        }
      }
    }

  }

}
