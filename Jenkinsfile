pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        sh 'g++ -o myExecutable working.cpp' 
        echo 'Build Stage Successful'
      }
    }
    stage('Test') {
      steps {
        sh './myExecutable' 
        echo 'Test Stage Successful'
        post {
          always {
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
    }
    stage ('Deploy') {
      steps { 
        echo 'Deployment successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
