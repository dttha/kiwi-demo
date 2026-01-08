pipeline {
    agent any

    parameters {
        string(name: 'KIWI_TAG', defaultValue: 'KIWI-LOGIN-001',
               description: 'Tag received from Kiwi TCMS')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Robot Tests') {
            steps {
                sh '''
                echo "Running tests with tag: ${KIWI_TAG}"
                find . -name "*.robot"

                /opt/robot-venv/bin/robot -i ${KIWI_TAG} tests/
                '''
            }
        }
    }
}
