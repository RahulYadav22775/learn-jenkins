pipeline {
    agent {
        label 'AGENT-1'
    }

    options {
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds()
        // retry(1)
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps{
                
                    sh ' echo this is Build '
                    // sh 'sleep 10'
            }
        }

        stage('Test') {
            steps{
                 
                    sh ' echo this is test'
                
            }
        }

        stage('Deploy') {
            when {
                expression { env.GIT_BRANCH = "origin/main" }
            steps{
                
                    sh ' echo this is deploy'
                    // error 'pipeline failed'
                
            }
        }

        stage('print params') {
            steps{
                echo " hello ${params.PERSON}"
                echo " biography: ${params.BIOGRAPHY}"
            }
        }
         // stage('Approval'){
        //     input {
        //         message "Should we continue?"
        //         ok "Yes, we should."
        //         submitter "alice,bob"
        //         parameters {
        //             string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        //         }
        //     }
        //     steps {
        //         echo "Hello, ${PERSON}, nice to meet you."
        //     }
        // }
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
}