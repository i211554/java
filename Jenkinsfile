pipeline {
    agent any
    tools {
        maven 'Maven' // Specify the Maven version configured in Jenkins
        jdk 'Java 11' // Specify the JDK version configured in Jenkins (optional, add if needed)
    }
    environment {
        // Variables defined here can be used by any stage
        NEW_VERSION = '1.3.0' // Example of an environment variable
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                // Using environment variable
                echo "Building version ${NEW_VERSION}"
                // Maven install command
                sh 'mvn install'
            }
        }
        stage('Test') {
            when {
                branch 'main' // Run this stage only on the 'main' branch
            }
            steps {
                echo 'Running Tests'
                // Maven test command
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Project'
                echo "Deploying version ${NEW_VERSION}"
                // Maven deploy command (example)
                sh 'mvn deploy'
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution completed'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
