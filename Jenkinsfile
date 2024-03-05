pipeline{
  agent any
  stages{
    stage("Build"){
      steps{
        build-error-here 'PES1UG21CS683-1'
        sh 'g++ working.cpp -o working'
      }
    }
    stage("Test"){
      steps{
        sh './working'
      }
    }
    stage("Deploy"){
      steps{
        echo 'Deploy'
      }
    }
  }
  post{
    failure{
      error 'Pipeline failed'
    }
  }
}
