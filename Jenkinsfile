pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/MelbinTomy/sample-ci-workflow.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the HTML project... (if needed)'
            }
        }
        stage('Test') {
            steps {
                echo 'Running basic tests... (e.g., checking if index.html exists)'
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
                echo 'Deploying HTML project...'
                // Add deployment logic here (e.g., FTP upload, cloud deployment, etc.)
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
