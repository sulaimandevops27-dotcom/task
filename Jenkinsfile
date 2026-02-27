pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/sulaimandevops27-dotcom/task.git'
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
            echo 'UI build completed successfully'
        }
        failure {
            echo 'UI build failed'
        }
    }
}
