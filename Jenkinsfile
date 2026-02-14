pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Show Branch') {
            steps {
                echo "Running on branch: ${env.BRANCH_NAME}"
            }
        }

        stage('Echo app.py File') {
            steps {
                sh 'echo "Printing app.py content below:"'
                sh 'cat app.py'
            }
        }

        stage('Run App (Only Development)') {
            when {
                branch 'development'
            }
            steps {
                sh 'python3 app.py &'
                sh 'sleep 5'
            }
        }

        stage('Deploy (Only Main)') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying Production Build..."
            }
        }
    }
}

