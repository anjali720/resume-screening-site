pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/anjali720/resume-screening-site.git'
        PROJECT_NAME = 'resume-screening-site'
    }

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Clone Repository') {
            steps {
                bat "git clone %REPO_URL%"
            }
        }

        stage('Start Containers') {
            steps {
                dir("${PROJECT_NAME}") {
                    bat 'docker-compose up -d'
                }
            }
        }

        stage('Verify Running Containers') {
            steps {
                bat 'docker ps -a'
            }
        }
    }
}