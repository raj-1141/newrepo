pipeline {
    agent any // Specifies that the pipeline can run on any available agent

    stages {
        stage('Code-Checkout') { // Defines the "Build" stage
            steps {
                echo 'Checking out the code in Jenkins workspace...' 
                git branch:'master', credentialsId: 'github-key', url: 'https://github.com/YadneshN/Demo_SL.git'
                sh 'ls -ltr'// Prints a message to the console
            }
        }
        stage('Build') { // Defines the "Build" stage
            steps {
                echo 'Building the application...' 
                sh 'ls -ltr'// Prints a message to the console
            }
        }

        stage('Test') { // Defines the "Test" stage
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') { // Defines the "Deploy" stage
            steps {
                echo 'Deploying the application...'
            }
        }
    }

    post { // Actions to perform after the pipeline completes
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
