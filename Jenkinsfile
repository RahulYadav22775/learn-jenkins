pipeline {
    agent any
    stages {
        stage('Build') {
            steps{
                script{
                    sh 'this is build'
                }

            }
        }

        stage('Test') {
            steps{
                 script{
                    sh 'this is test'
                }
            }
        }

        stage('Deploy') {
            steps{
                script{
                    sh 'this is deploy'
                }
            }
        }
    }
}