pipeline {
    agent any  // Runs on any available Jenkins agent
    
    stages {
        stage('Checkout') {
            steps {
                // Pull the latest code from the Git repository
                git 'https://github.com/MelbinTomy/sample-ci-workflow.git'
            }
        }
        
        stage('Test') {
            steps {
                // Perform a basic check (e.g., check if the HTML file exists)
                script {
                    def file = 'index.html'
                    if (fileExists(file)) {
                        echo "${file} exists!"
                    } else {
                        error "${file} does not exist!"
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                // For this example, we're just printing a message as deployment.
                echo 'Deploying the HTML project to the web server...'
                // Here you could add steps to deploy, e.g., copying files to a server or uploading to a CDN.
            }
        }
    }
    
    post {
        always {
            // Clean up workspace after the pipeline runs
            cleanWs()
        }
        
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the logs for details.'
        }
    }
}
