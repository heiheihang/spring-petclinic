pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh './mvnw package'

            }
        }
       stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
            steps{
                    withSonarQubeEnv('sonarqube-9.1') 
                { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
                    sh "mvn sonar:sonar"
                }
            }
        }
    }

  }
}