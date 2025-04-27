pipeline {
    agent any

    stages {
        stage('Setup Python Virtual Environment') {
            steps {
                bat 'python -m venv venv'
            }
        }

        stage('Activate and Install Dependencies') {
            steps {
                bat 'call venv\\Scripts\\activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'call venv\\Scripts\\activate && pytest test_hello.py'
            }
        }

        stage('Post Actions') {
            steps {
                echo 'Cleaning up...'
                deleteDir()
                echo 'Build and Tests passed!'
            }
        }
    }
}
