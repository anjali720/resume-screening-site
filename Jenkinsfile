pipeline {
    agent any

    stages {
        stage('Check File') {
            steps {
                // Use 'bat' for Windows
                bat 'dir'
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo Deploy step'
            }
        }
    }
}

}
