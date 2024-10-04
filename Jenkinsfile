
pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Clona il repository dal Git configurato
                git branch: 'master', url: 'https://github.com/Crixsteen/django-rest-framework.git'
            }
        }

        stage('Build') {
            steps {
                // Aggiungi qui i comandi di build
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                // Esegue i test
                echo 'Running tests...'
                sh 'pytest'  // Assicurati di avere pytest configurato
            }
        }

        stage('Deploy') {
            steps {
                // Aggiungi qui i comandi di deploy
                echo 'Deploying the project...'
            }
        }
    }

    post {
        always {
            // Notifica se qualcosa va storto
            echo 'Pipeline completed'
        }
    }
}


