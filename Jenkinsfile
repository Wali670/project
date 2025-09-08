pipeline {
    agent any
    environment {
        NETLIFY_AUTH_TOKEN = credentials('NETLIFY_AUTH_TOKEN')
        NETLIFY_SITE_ID = 'dc50f1f9-6d40-45ec-9ccb-f5fd4e126435'
  
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