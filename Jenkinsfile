pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/anjali702/devops-site.git'
            }
        }
        stage('Check File') {
            steps {
                sh 'ls | grep devops.html'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying your application...'
            }
        }
    }
}
