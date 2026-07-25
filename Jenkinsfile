pipeline {
    agent any

    environment {
        APP_NAME   = 'MyApp'
        DEPLOY_ENV = 'production'
        COURCE     = 'Jenkins'
    }
    options{
        timeout(time: 10, unit: 'minutes')
    }

    stages {

        stage('Build') {
            steps {
                sh """
                    echo "Environment source: ${COURCE}"
                    echo "Application: ${APP_NAME}"
                    echo "Deployment environment: ${DEPLOY_ENV}"
                    echo "Building..."
                """
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to ${DEPLOY_ENV}..."
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
            cleanWs()
        }
    }
}