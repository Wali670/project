pipeline {
    agent any
    environment {
        NETLIFY_AUTH_TOKEN = credentials('NETLIFY_AUTH_TOKEN')
        NETLIFY_SITE_ID = 'f39cec1a-3d67-4a9f-ad99-2afa522d6044'
  
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Netlify CLI') {
            steps {
                bat 'npm install netlify-cli'
            }
        }
        stage('Deploy to Netlify') {
            steps {
                bat 'npx netlify deploy --dir=. --prod --auth=%NETLIFY_AUTH_TOKEN% --site=%NETLIFY_SITE_ID%'
            }
        }
    }
}