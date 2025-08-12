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
                // The 'sh' command executes a shell command.
                // This command copies all files from the current directory (the workspace)
                // to a local folder you create for this purpose.
                sh 'cp -r ./* /var/www/html'
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
