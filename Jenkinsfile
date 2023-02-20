pipeline {
    agent any
    triggers { 
        pollSCM('0 * * * *')
    }
    options {
        fastFail()
        timestamps ()
        timeout(time: 2, unit: 'MINUTES')   
        skipDefaultCheckout true
        buildDiscarder(logRotator(numToKeepStr: '2'))
    }
    stages {
        stage('Stage 1') {
            steps {
                script {
                env.selected_environment = input  message: 'Select environment to Deploy',ok : 'Proceed',id :'tag_id',
                parameters:[choice(choices: ['DEV', 'QA', 'STAGING', 'PROD'], description: 'Select environment', name: 'env')]
                echo "Deploying in ${env.selected_environment}."
                }
            }
        }
    }
    post { 
    always { 
            echo 'Congratulations'
        }
    }
}    
