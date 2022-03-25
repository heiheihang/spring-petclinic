pipeline {
    agent any
    environment {   
        PATH = "/usr/share/maven/bin"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn clean package'

            }
        }
       stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
            steps{
                    withSonarQubeEnv('devops class') 
                { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
                    sh "mvn sonar:sonar"
                }
            }
        }
    }

}