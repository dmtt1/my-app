pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                git 'https://github.com/dmtt1/my-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat '''
                python -m venv venv
                call venv\\Scripts\\activate
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                bat '''
                call venv\\Scripts\\activate
                python -m unittest discover
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy successful!'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished!'
        }
    }
}
