pipeline {
    agent any

    environment {
        PROJECT_DIR = "/Users/yograj/projects/sample"
        TEST_ENVIRONMENT = "staging"
        PRODUCTION_ENVIRONMENT = "production"
    }

    stages {

        stage('Build') {
            steps {
                echo 'Fetching source code...'
                echo "Project Directory: ${env.PROJECT_DIR}"
                echo 'Compiling the project and generating artifacts...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                echo 'Running integration tests...'
            }
        }

        stage('Code Quality Check') {
            steps {
                echo 'Checking code quality and security...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying application to ${env.TEST_ENVIRONMENT} environment..."
            }
        }

        stage('Approval') {
            steps {
                echo 'Waiting for manual approval (simulated)...'
                sleep(time: 10, unit: 'SECONDS')
                echo 'Approval received.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying application to ${env.PRODUCTION_ENVIRONMENT} environment..."
            }
        }
    }

    post {
        always {
            echo "Pipeline finished with status: ${currentBuild.currentResult}"
        }
    }
}
