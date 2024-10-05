pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/Crixsteen/django-rest-framework.git'
            }
        }

        stage('Install') {
            steps {
                // Verifica la versione di Python
                sh 'python3 --version || python --version'
                
                // Assicura che pip sia installato
                sh 'python3 -m ensurepip --upgrade || python -m ensurepip --upgrade'
                
                // Installa pytest
                sh 'pip3 install pytest || pip install pytest'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'pytest'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed'
        }
    }
}

