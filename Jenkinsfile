pipeline {

    agent any

    environment {
        APP_NAME   = 'MyApp'
        DEPLOY_ENV = 'production'
        COURCE     = 'Jenkins'
    }
    options{
        timeout(time: 1, unit: 'MINUTES')
    }

    parameters {
        string(name: 'APP_NAME', defaultValue: 'MyApp', description: 'Application name')
        choice(name: 'DEPLOY_ENV', choices: ['development', 'staging', 'production'], description: 'Deployment environment')
        string(name: 'COURCE', defaultValue: 'Jenkins', description: 'Environment source')
    }


    stages {
        stage('Build') {
            steps {
                sh """
                    echo "Environment source: ${COURCE}"
                    echo "Application: ${APP_NAME}"
                    echo "Deployment environment: ${DEPLOY_ENV}"
                   
                    sleep 10
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
        aborted {
            echo 'Pipeline was aborted!'
        }
    }
}