pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'chmod +x mvnw'
                sh './mvnw -B clean compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './mvnw -B test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging the application...'
                sh './mvnw -B package'
            }
        }
    }
}
