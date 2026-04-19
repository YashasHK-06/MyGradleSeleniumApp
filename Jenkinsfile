pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Yashaswiiii8/MyGradleSeleniumApp.git'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew :app:build -Dorg.gradle.java.home=/opt/jdk17'
            }
        }

        stage('Run Selenium') {
            steps {
                sh './gradlew :app:run -Dorg.gradle.java.home=/opt/jdk17'
            }
        }
    }

    post {
        success {
            echo 'Gradle Selenium execution successful ✅'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
