pipeline {
    agent any

    tools {
        nodejs 'NodeJS-22'
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('Documents/dev/welcome-react') {
                    bat 'npm install'
                }
            }
        }

        stage('Build React App') {
            steps {
                dir('Documents/dev/welcome-react') {
                    bat 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo 'Build successful ✅'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
