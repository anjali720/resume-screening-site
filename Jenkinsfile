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

    post {
        success {
            mail to: 'anjalitanu20@gmail.com',
                 subject: "✅ Build Success - #${env.BUILD_NUMBER}",
                 body: """
    🎉 Congratulations! The Jenkins pipeline has successfully completed all stages.
    Your project is now ready and deployed, and everything is running smoothly.

    The details are mentioned below:

    📄 Job Name: ${env.JOB_NAME}
    🔢 Build Number: ${env.BUILD_NUMBER}
    🌿 Branch: ${env.GIT_BRANCH}
    🔗 Build URL: ${env.BUILD_URL}
    🕒 Timestamp: ${new Date()}
    ⏱ Duration: ${currentBuild.durationString}

    ✅ Status: SUCCESS
    """
        }
        failure {
            mail to: 'anjalitanu20@gmail.com',
                 subject: "❌ Build Failed - #${env.BUILD_NUMBER}",
                 body: """
    ⚠️ Unfortunately, the pipeline encountered an error during execution.
    The details are mentioned below:

    📄 Job Name: ${env.JOB_NAME}
    🔢 Build Number: ${env.BUILD_NUMBER}
    🌿 Branch: ${env.GIT_BRANCH}
    🔗 Build URL: ${env.BUILD_URL}
    🕒 Timestamp: ${new Date()}
    ⏱ Duration: ${currentBuild.durationString}

    ❌ Status: FAILURE

    Please check the Jenkins console output for more details and to investigate the cause of the failure.
    """
        }
    }
}