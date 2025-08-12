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
                // Use a batch command and a Windows-style path
                bat 'C:\\Windows\\System32\\cmd.exe /c xcopy /E /Y .\\* C:\\deployed_website\\'
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
