pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'GitHub repository checkout completed.'
            }
        }

        stage('Build') {
            steps {
                echo 'Build started.'
                bat 'echo Build success > build-result.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Test started.'
                bat 'echo Test success >> build-result.txt'
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully.'
            archiveArtifacts artifacts: 'build-result.txt', fingerprint: true
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
