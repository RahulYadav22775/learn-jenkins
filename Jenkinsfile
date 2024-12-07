pipeline {
    agent {
        label 'AGENT-1'
    }
    stages {
        stage('Build') {
            steps{
                
                    sh ' echo this is build'
                

            }
        }

        stage('Test') {
            steps{
                 
                    sh ' echo this is test'
                
            }
        }

        stage('Deploy') {
            steps{
                
                    sh ' echo this is deploy'
                
            }
        }
    }

    post {
        always {
            echo " this section always runs"
        }

        success {
            echo " this section runs when pipeline is success"
        }
        failure {
            echo " this section runs when pipeline is failed"
        }
    }

}