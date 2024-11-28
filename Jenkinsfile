pipeline {
    agent any
    environment {
        // Define custom environment variables
        TOOL_VERSION = '1.2.3'   // Example: a specific tool version
        DEPLOY_ENV = 'production' // Deployment environment
    }
    stages {
        stage('Build') {
            steps {
                echo "Building with tool version ${TOOL_VERSION}"
                // Use the TOOL_VERSION environment variable in build commands
                sh 'echo Building with version $TOOL_VERSION'
            }
        }
        stage('Test') {
            steps {
                echo "Testing in ${DEPLOY_ENV} environment"
                // Use the DEPLOY_ENV environment variable in test commands
                sh 'echo Running tests in $DEPLOY_ENV'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying to ${DEPLOY_ENV}"
                // Use the environment variables during deployment
                sh 'echo Deploying to $DEPLOY_ENV using version $TOOL_VERSION'
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
