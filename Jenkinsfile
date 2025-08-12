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
                // Create the deployment directory first
                bat 'mkdir C:\\deployed_website'
                // Then, copy the files into it
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
