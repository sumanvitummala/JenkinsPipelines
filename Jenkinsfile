pipeline {
    agent any  // run on any available Jenkins agent

    stages {
        stage('Checkout') {
            steps {
                // Pull the HTML project from GitHub
                git url: 'https://github.com/sumanvitummala/Jenkins-project1.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // For HTML, there is usually no compilation, just verify files
                echo 'Build Step: HTML project does not require compilation'
                sh 'ls -l'  // list project files to verify checkout
            }
        }

        stage('Test') {
            steps {
                // Simple test: check if index.html exists
                sh '''
                if [ -f index.html ]; then
                    echo "index.html exists - test passed"
                else
                    echo "index.html missing - test failed"
                    exit 1
                fi
                '''
            }
        }

        stage('Post-Build / Deploy') {
            steps {
                // Optional: copy files to a staging folder or server
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

