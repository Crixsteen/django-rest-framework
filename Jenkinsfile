pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/Crixsteen/django-rest-framework.git'
            }
        }

        stage('Install Python & pip') {
            steps {
                // Installa Python e pip se non sono presenti
                sh '''
                    if ! command -v python3 &> /dev/null; then
                        echo "Python3 non trovato. Installo Python3."
                        sudo apt-get update
                        sudo apt-get install -y python3 python3-pip
                    fi
                    python3 --version
                    pip3 --version

                '''
            }
        }

        stage('Install pytest') {
            steps {
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

