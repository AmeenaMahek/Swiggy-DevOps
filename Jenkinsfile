pipeline {
    agent any

    tools {
        sonarRunner 'SonarScanner'
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
