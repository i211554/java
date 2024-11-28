pipeline {
    agent any

    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod') // String parameter
        choice(name: 'VERSION_CHOICE', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Choose version') // Choice parameter
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run the Test Stage') // Boolean parameter
    }

    environment {
        NEW_VERSION = '1.3.0' // Example variable accessible to all stages
    }

    stages {
        stage('Build') {
            steps {
                echo "Building Project for Version: ${params.VERSION_CHOICE}"
            }
        }

        stage('Test') {
            when {
                expression {
                    // Check the 'executeTests' parameter
                    params.executeTests
                }
            }
            steps {
                echo 'Testing Project...'
            }
        }
    }
}
