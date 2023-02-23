pipeline {
    agent any
    options{
        timestamps()
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'apt install nodejs'
                    // Check if the build was successful
                    if (currentBuild.result != 'SUCCESS') {
                        error('Build failed!')
                    }
                }
            }
        }
    }
}
