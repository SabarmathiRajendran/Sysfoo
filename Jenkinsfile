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
                archiveArtifacts artifacts: '**/*.war', fingerprint: true 
            }
       }
    }
}

