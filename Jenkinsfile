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
                // Installa pytest
                sh 'pip install pytest'
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



