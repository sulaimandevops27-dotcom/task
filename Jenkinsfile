pipeline {
    agent any

    stages {

        stage('Setup NodeJS') {
            steps {
                script {
                    env.NODEJS_HOME = tool name: 'NodeJS', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
                    env.PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
                }

                sh 'node -v'
                sh 'npm -v'
            }
        }

        stage('Checkout Code') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/sulaimandevops27-dotcom/task.git'
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
