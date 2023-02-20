pipeline {
    agent any
    triggers { 
        pollSCM('0 * * * *')
    }
    options {
        timestamps ()
        timeout(time: 2, unit: 'MINUTES')   
        skipDefaultCheckout true
        buildDiscarder(logRotator(numToKeepStr: '2'))
    }
    stages {
        stage('Stage 1') {
            steps {
                input {
                message "Can we Proceed?"
                ok "Yes"
                submitter "Sharanya Jayaram"
                parameters {
                    string(name: 'DEVELOPER', description: 'Member')
                }
            }
            steps {
                echo "${DEVELOPER}, is proceeding..."
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
