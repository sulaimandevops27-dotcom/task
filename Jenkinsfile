stage('Setup Node') {
    steps {
        script {
            env.NODEJS_HOME = tool name: 'NodeJS', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
            env.PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
        }
        sh 'node -v'
        sh 'npm -v'
    }
}
