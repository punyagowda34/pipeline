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
                sh 'mkdir -p out'
                sh 'javac -d out src/*.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'java -cp out test.MainTest'
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving build artifacts...'
                archiveArtifacts artifacts: 'out/*.class', fingerprint: true
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
