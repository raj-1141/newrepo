pipeline {
    agent any // Specifies that the pipeline can run on any available agent

    stages {
        stage('Build') { // Defines the "Build" stage
            steps {
                echo 'Building the application...' 
                sh 'docker build -t python-app:v1 .' 
            }
        }

        stage('Build-Test') { // Defines the "Test" stage
            steps {
                echo 'Running tests...'
                sh 'docker images'
            }
        }

        stage('Deploy') { // Defines the "Deploy" stage
            steps {
                echo 'Deploying the application...'
                sh 'docker run -d --name myapp python-app:v1'
            }
        }

        stage('Deploy-Test') { // Defines the "Test" stage
            steps {
                echo 'Running tests...'
                sh 'docker ps -a'
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
