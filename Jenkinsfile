pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                bat 'echo Cloning...'
                // Normally Git is handled by Jenkins when using Git SCM
            }
        }

        stage('Build') {
            steps {
                bat 'echo Building project...'
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo Deploying...'
            }
        }
    }
}
