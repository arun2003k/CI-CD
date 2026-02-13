pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Python App') {
            steps {
                sh '''
                echo "Running app.py..."
                python3 app.py
                '''
            }
        }
    }
}


