pipeline {
    agent any

    environment {
        SONARQUBE = 'Local SonarQube'
    }

    stages {

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t swiggy-app .'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('Local SonarQube') {
                    sh 'sonar-scanner'
                }
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8080:8080 swiggy-app || true'
            }
        }
    }
}


