pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/Crixsteen/django-rest-framework.git'
            }
        }

        stage('Run in Docker') {
            steps {
                // Esegui il codice nel container Docker Python 3.9
                sh '''
                    docker run --rm -v $(pwd):/app -w /app python:3.9 bash -c "
                    pip install pytest &&
                    pytest
                    "
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed'
        }
    }
}


