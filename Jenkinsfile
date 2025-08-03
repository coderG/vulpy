pipeline {
    agent any

    environment {
        SONARQUBE_ENV = 'SonarScannerManual'  // must match configured server name in Jenkins
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
                    bat 'sonar-scanner'
                }
            }
        }
    }
}
