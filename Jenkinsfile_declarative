pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'mvn clean package' 
            }
        }
       stage('Archieve') { 
            steps {
                sh 'make'
                archiveArtifacts artifacts: '**/*.war', fingerprint: true 
            }
       }
    }
}

