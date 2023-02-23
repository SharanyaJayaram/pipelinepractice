pipeline {
    agent any
    options{
        timestamps()
    }
    
    stages {
        stage('Build') {
            steps {
                apt install nodejs
                script {
                    // Check if the build was successful
                    if (currentBuild.result != 'SUCCESS') {
                        error('Build failed!')
                    }
                }
            }
        }
    }
}
