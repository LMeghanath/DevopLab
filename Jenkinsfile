pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning the project from Git...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the website locally...'
                // The 'bat' command executes a Windows command
                // 'xcopy' is used for copying files and directories on Windows
                bat 'xcopy /E /Y .\\* C:\\deployed_website\\'
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully! 🎉'
        }
        failure {
            echo 'Deployment failed! 😭'
        }
    }
}
