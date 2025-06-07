pipeline {
    agent any

    options {
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds()
        // retry(1)
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        // password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo this is Build'
            }
        }

        stage('Test') {
            steps {
                sh 'echo this is testing stage'
            }
        }

        stage('Deploy') {
            when {
                expression { env.GIT_BRANCH == "origin/main" }
            }
            steps {
                sh 'echo this is deploy stage'
                // error 'pipeline failed'
            }
        }

        stage('Print Params') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "TOGGLE: ${params.TOGGLE}"
            }
        }
    }

    post {
        always {
            echo "This section always runs"
            // deleteDir()
        }
        success {
            echo "This section runs when pipeline is successful"
        }
        failure {
            echo "This section runs when pipeline fails"
        }
    }
}
