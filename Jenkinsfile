pipeline {
    agent any

    stages {
        stage('SonarQube Analysis') {
            steps {
                echo 'Running SonarQube analysis...'

                withSonarQubeEnv('Local SonarQube') {
                    script {
                        def scannerHome = tool 'SonarScanner'
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
