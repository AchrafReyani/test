pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Ensure the workspace is clean
                    deleteDir()

                    // Clone the repository (you can adjust the repository URL)
                    checkout scm

                    // Run a simple HTTP server to serve the HTML file
                    sh 'python3 -m http.server 8000 &'

                    // Wait for the server to start (adjust the sleep time if needed)
                    sleep 10

                    // Run a simple test to check if the HTML file is accessible
                    sh 'curl http://localhost:8000/index.html'
                }
            }
        }
    }

    post {
        always {
            // Stop the HTTP server when the pipeline is finished
            sh 'kill $(lsof -t -i:8000)'
        }
    }
}
