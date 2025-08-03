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
                    bat 'sonar-scanner'
                }
            }
        }
    }
}
