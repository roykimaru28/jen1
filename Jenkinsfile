pipeline{
    agent {
        label 'slave1'
    }
    stages {
        stage ('stepone'){
            parallel{
                stage ('stepone stage one'){
                    steps{
                        echo "This is stepone stage one"
                    }
                }
                stage ('stepone stage two'){
                    steps{
                        echo " This is stepone stage two"
                    }
                }
                stage ('stepone stage three'){
                    agent{
                        label 'slave2'
                    }
                    steps{
                        echo "This is step three"
                    }
                }
            }
        }
        stage('steptwo'){
            parallel{
                stage('steptow stage one'){
                    agent{
                        label 'slave1'
                    }
                    steps{
                        echo "This is steptwo stage one"
                    }
                }
                stage('steptwo stage two'){
                    steps{
                        echo "This is steptwo stage two"
                    }
                }
            }
        }
        stage('stepthree'){
            agent{
                label 'slave2'
            }
            steps{
                echo "This is step three"
            }
        }
        stage('stepfour'){
            parallel{
                stage('stepfour stage one'){
                    when{
                        branch 'feature'
                    }
                    steps{
                        echo "I am sleeping"
                    }
                }
                stage('stepfour'){
                    steps{
                        echo "This is up"
                    }
                }
                stage('last step'){
                    steps{
                        echo "The last build"
                    }
                }
            }
        }
        stage('scripted'){
            steps{
                sh 'ps -ef'
            }
        }
    }
}
