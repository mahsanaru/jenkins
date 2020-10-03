pipeline {
  agent none

  stages {
    stage("Test back end") {
      agent {
        dockerfile {
          filename "back-end/dockerfiles/ci/Dockerfile"
        }
      }

      steps {
        sh "cd back-end && bin/ci"
      }
    }
  }
}
