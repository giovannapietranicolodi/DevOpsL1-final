pipeline {
    agent any

    environment {
        FIREBASE_TOKEN = credentials('firebase-token')
    }

    stages {

        stage('Build') {
            steps {
                echo 'Installing Firebase Tools...'
                sh 'npm install -g firebase-tools'
                sh 'firebase --version'
            }
        }

        stage('Testing') {
            steps {
                echo 'Deploying to Testing environment...'
                sh 'firebase deploy --only hosting --project final-gpn --token $FIREBASE_TOKEN'
            }
        }

        stage('Staging') {
            steps {
                echo 'Deploying to Staging environment...'
                sh 'firebase deploy --only hosting --project final-gpn-stg --token $FIREBASE_TOKEN'
            }
        }

        stage('Production') {
            steps {
                echo 'Deploying to Production environment...'
                sh 'firebase deploy --only hosting --project gpn-default --token $FIREBASE_TOKEN'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully! All environments deployed.'
        }
        failure {
            echo 'Pipeline failed. Check logs above for details.'
        }
    }
}
