pipeline {
    agent {
        // Utilizza l'immagine Docker di Python 3.9
        docker { image 'python:3.9' }
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/Crixsteen/django-rest-framework.git'
            }
        }

        stage('Install pytest') {
            steps {
                // Installa pytest utilizzando pip
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


