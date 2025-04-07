pipeline {
    agent any

    environment {
        // Define any environment variables here
        MY_ENV_VAR = 'some_value'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from a Git repository
                git 'https://github.com/your-repository/your-project.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build the project (this can be a Maven, Gradle, or any other build tool command)
                    echo "Building the project"
                    sh './gradlew build'  // Example using Gradle
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run tests (could be unit tests, integration tests, etc.)
                    echo "Running tests"
                    sh './gradlew test'  // Example using Gradle
                }
            }
        }

        stage('Deploy') {
            when {
                // Only deploy if tests pass (default behavior if the tests pass)
                branch 'main'  // Make sure deploy only runs on the main branch
            }
            steps {
                script {
                    // Deployment script (e.g., deploying to a server)
                    echo "Deploying the application"
                    sh './deploy.sh'  // Example deploy script
                }
            }
        }
    }

    post {
        always {
            // Clean up actions, like archiving logs, etc.
            echo "Cleaning up"
        }

        success {
            // Actions to take if the pipeline is successful (e.g., sending notifications)
            echo "Pipeline succeeded!"
        }

        failure {
            // Actions to take if the pipeline fails (e.g., sending failure notifications)
            echo "Pipeline failed!"
        }
    }
}
