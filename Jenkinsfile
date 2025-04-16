pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/anjali702/devops-site.git'
            }
        }

        stage('Check File') {
            steps {
                sh 'ls -l devops.html'
            }
        }

        stage('Deploy') {
            steps {
                echo 'In real case, deploy HTML to server or S3 bucket'
               
            }
        }
    }
}
