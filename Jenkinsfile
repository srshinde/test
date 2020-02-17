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
            steps {
                echo 'Deploying'
            }\
            }
        }
    }
  post {
    success {
      slackSend color: "good", message: "${JOB_NAME} ${currentBuild.displayName} passed: ${BUILD_URL} in ENV"
    }
    failure {
      slackSend color: "danger", message: "${JOB_NAME} ${currentBuild.displayName} failed: ${BUILD_URL} in ENV"
    }
  }
}
