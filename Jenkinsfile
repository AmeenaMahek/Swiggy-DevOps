pipeline {
    agent any

    environment {
        SONARQUBE = 'Local SonarQube'
    }

    stages {

        stage('SonarQube Analysis') {
            steps {
                echo 'Running SonarQube analysis...'
                withSonarQubeEnv('Local SonarQube') {
                    sh 'sonar-scanner'
                }
            }
        }

    }
}



