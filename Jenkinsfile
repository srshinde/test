pipeline {
    agent any
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            when {
                branch 'production'
            }
            step {
                echo 'Deploying'
            }
        }
    }
  post {
    failure {
      slackSend color: "danger", message: "${JOB_NAME} ${currentBuild.displayName} failed: ${BUILD_URL} in ENV"
    }
    success {
      slackSend color: "good", message: "${JOB_NAME} ${currentBuild.displayName} passed: ${BUILD_URL} in ENV"
    }
  }
}
