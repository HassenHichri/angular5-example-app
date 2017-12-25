pipeline {
    agent any

    stages {
        stage('NPM Install') {
                withEnv(["NPM_CONFIG_LOGLEVEL=warn"]) {
                    sh 'npm install'
                }
        }

        stage('Lint') {
                sh 'npm run lint'
        }

        stage('Test') {
           withEnv(["CHROME_BIN=/usr/bin/chromium-browser"]) {
            sh 'npm run test'
            sh 'npm run e2e'
                }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}