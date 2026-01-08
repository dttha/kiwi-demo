pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Robot Tests') {
            steps {
                sh '''
                find . -name "*.robot"
                /opt/robot-venv/bin/robot tests/
                '''
            }
        }
    }
}
