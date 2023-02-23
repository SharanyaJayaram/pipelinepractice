pipeline {
    agent any
    options{
        timestamps()
        buildDiscarder(logRotator(numToKeepStr: '2'))
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building"
                    // Check if the build was successful
                    if (currentBuild.result != 'SUCCESS') {
                        error('Build failed!:${env.BUILD_NUMBER}')
                    }
                }
            }
        }
    }
}
