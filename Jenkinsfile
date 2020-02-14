pipeline {
    agent any
    stages { 
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
    }
  post {
    success {
      slackSend color: "good", message: "${JOB_NAME} ${currentBuild.displayName} passed: ${BUILD_URL} in ENV: ${ENV}"
    }
    failure {
      slackSend color: "danger", message: "${JOB_NAME} ${currentBuild.displayName} failed: ${BUILD_URL} in ENV: ${ENV}"
    }
  }
}
