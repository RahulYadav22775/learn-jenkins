pipeline {
    agent {
        label 'AGENT-1'
    }

    options {
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds()
        retry(1)
    }
    stages {
        stage('Build') {
            steps{
                
                    sh ' echo this is build'
                    // sh 'sleep 10'
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
                    error 'pipeline failed'
                
            }
        }
    }

    post {
        always {
            echo " this section always runs"
            // deleteDir()
        }

        success {
            echo " this section runs when pipeline is success"
        }
        failure {
            echo " this section runs when pipeline is failed"
        }
    }

}