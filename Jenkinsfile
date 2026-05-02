  pipeline {
    agent any

    environment {
        // Store your Vercel token in Jenkins credentials
        VERCEL_TOKEN = credentials('vercel_token')
    }

    stages {

        stage('Install') {
            steps {
                // Install dependencies
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Optional test stage (you can replace with real tests)
                echo 'Skipping tests - no test script found'
            }
        }

        stage('Build') {
            steps {
                // Build Next.js app
                bat 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy to Vercel using token
                bat 'npx vercel --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
    }
}