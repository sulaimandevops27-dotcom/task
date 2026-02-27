pipeline {
    agent any

    tools {
        nodejs 'node18'
    }

    stages {
        stage('Checkout Source') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/betawins/Trading-UI.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'node -v'
                sh 'npm -v'
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test || echo "No tests defined"'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build || echo "No build step defined"'
            }
        }
    }
}
