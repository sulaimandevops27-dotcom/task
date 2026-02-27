pipeline {
    agent any

    tools {
        nodejs "nodejs"
    }

    stages {
        stage('Checkout Code') {
            steps {
                branch: 'master',
                    url: 'https://github.com/saivicky123/Trading-UI.git'
            }
        }

        stage('Verify Node & NPM') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build UI') {
            steps {
                sh 'CI=false npm run build'
            }
        }
    }

    post {
        success {
            echo ‘UI build completed successfully'
        }
        failure {
            echo 'UI build failed'
        }
    }
}
