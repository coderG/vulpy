pipeline {
    agent any

    tools {
        sonarScanner 'SonarScanner'
    }

    stages {
        stage('SCM') {
            steps {
                checkout scm
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'sonar-scanner'
                }
            }
        }
    }
}
