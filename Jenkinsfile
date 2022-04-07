pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                    sh 'mvn clean package'

            }
        }
       stage('Ansible Deploy') {
//    def scannerHome = tool 'SonarScanner 4.0';
            steps{
                sh 'ansible-playbook playbook.yml'
            }
        }
    }

}