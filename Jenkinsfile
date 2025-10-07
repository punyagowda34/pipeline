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
                bat 'echo Building completed successfully! > build_output.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo All tests passed successfully! > test_result.txt'
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving artifacts...'
                bat 'echo Archiving files... > archive_note.txt'
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
