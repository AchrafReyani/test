pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Clean workspace
                    deleteDir()

                    // Clone repository
                    checkout scm

                    // Print the contents of the HTML file
                    sh 'cat index.html'
                }
            }
        }
    }
}
