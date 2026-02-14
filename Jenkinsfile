pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building branch: ${env.BRANCH_NAME}"
                sh 'python3 --version'
            }
        }

        stage('Test') {
            when {
                branch 'development'
            }
            steps {
                echo "Running tests on development branch"
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying to production"
            }
        }
    }
}
