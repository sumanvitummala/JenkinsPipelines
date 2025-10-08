pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                git branch: 'main', url: 'https://github.com/sumanvitummala/JenkinsPipelines.git'
            }
        }

        stage('Lint') {
            steps {
                echo 'Running lint checks...'
                sh 'npm install'
                sh 'npm run lint'
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving files...'
                archiveArtifacts artifacts: '**/*', allowEmptyArchive: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs.'
        }
    }
}
