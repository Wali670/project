pipeline {
    agent any
    environment {
        NETLIFY_AUTH_TOKEN = credentials('NETLIFY_AUTH_TOKEN')
        NETLIFY_SITE_ID = '8f70e12d-2c0d-464d-aac4-93633c2c75c6'
  
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