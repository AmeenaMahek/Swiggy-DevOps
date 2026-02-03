pipeline {
    agent any

    environment {
        SONARQUBE = 'Local SonarQube' // The name you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/AmeenaMahek/Swiggy-DevOps.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t swiggy-app .'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('Local SonarQube') {
                    bat 'sonar-scanner'
                }
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker run -d -p 8080:8080 swiggy-app'
            }
        }
    }
}

