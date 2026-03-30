pipeline {
    agent {
        node {
            label 'agent-1'
        }
    }
    environment {
        GREETING = 'Hello Jenkins'
    }
    stages {
        stage('Build'){
            steps{
                echo 'Building'
            }
        }
        stage('Test'){
            steps{
                echo 'Testing'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying'
                sh """
                    echo "Shell Script"
                    echo $GREETING
                """
            }
        }
    }
    post {
        always {
            echo 'this will run every time'
        }
        failure {
            echo 'this will run when there is failure'
        }
        success {
            echo 'this will run when there is success'
        }
    }
}
