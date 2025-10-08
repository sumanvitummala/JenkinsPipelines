pipeline {
    agent any  // Run on any available Jenkins agent

    stages {
        stage('Checkout') {
            steps {
                // Pull the HTML project from GitHub
                git url: 'https://github.com/sumanvitummala/Jenkins-project1.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // HTML doesn't require compilation, just verify files
                echo 'Build Step: HTML project does not require compilation'
                bat 'dir'  // List files in workspace
            }
        }

        stage('Test') {
    steps {
        bat '''
        cd project-1
        if exist index.html (
            echo index.html exists - test passed
        ) else (
            echo index.html missing - test failed
            exit /b 1
        )
        '''
    }
}


        stage('Post-Build / Deploy') {
            steps {
                echo 'Post-Build Step: Ready for deployment or archiving'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
