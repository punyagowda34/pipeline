pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/punyagowda34/pipeline.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'echo Building completed successfully!'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo All tests passed successfully!'
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving artifacts...'
                bat 'echo Build artifacts are being archived.'
                archiveArtifacts artifacts: '**/*.txt', fingerprint: true
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
