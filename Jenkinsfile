pipeline {
    agent any  
    stages {
        stage('Build') {
            steps {
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
                echo "Deploying to ${APP_ENV}..."
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
