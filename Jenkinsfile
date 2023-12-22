pipeline{
  agent any 
  stages{
    stage('stage-one'){
      steps{
        sh 'actionone'
      }
    }
    stage('stagetwo'){
      steps{
        echo "actiontwo"
      }
    }
    stage('stage3'){
      steps{
        sh 'df -h'
      }
    }
    stage('stage4'){
      steps{
        sh 'lscpu'
      }
    }
  }
}
