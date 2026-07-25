pipeline {
    agent any  

environment {
        // Define environment variables here
        APP_NAME = 'MyApp'
        DEPLOY_ENV = 'production'
        COURCE = " Jenkins"

    stages {
        stage('Build') {
            steps {
                sh """
                echo "environment cource:" ${COURCE}
                echo 'Building...'
                
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'               
            }
        }

        stage('Deploy') {
           
            steps {
                echo "Deploying to ..."
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
        always {
            cleanWs() // Clean workspace after run
        }
    }
}
