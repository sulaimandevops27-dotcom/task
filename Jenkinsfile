pipeline {
    agent any

    stages {

        stage('Install NodeJS Automatically') {
            steps {
                sh '''
                if ! command -v node > /dev/null 2>&1; then
                    echo "Node not found. Installing NodeJS..."
                    curl -fsSL https://rpm.nodesource.com/setup_18.x | sudo bash -
                    sudo yum install -y nodejs
                else
                    echo "Node already installed"
                fi
                '''
            }
        }

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
