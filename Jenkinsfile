pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/YashasHK-06/MyGradleSeleniumApp.git'
            }
        }

        stage('Setup Permissions') {
            steps {
                sh 'chmod +x gradlew'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew :app:build'
            }
        }

        stage('Run Selenium') {
            steps {
                sh './gradlew :app:run'
            }
        }
    }

    post {
        success {
            echo 'Gradle Selenium execution successful'
        }
        failure {
            echo 'Build failed'
        }
    }
}
