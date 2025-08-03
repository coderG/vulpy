pipeline {
    agent any

    environment {
        SONARQUBE_ENV = 'SonarQube' // Must match Jenkins SonarQube server name
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv("${SONARQUBE_ENV}") {
                    bat 'E:\sonar-scanner-cli-5.0.1.3006-windows\bin\sonar-scanner.bat'
                }
            }
        }
    }
}
