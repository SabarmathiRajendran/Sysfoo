pipeline {
  agent any
  stages{
    stage('Build'){
      steps{ 
        sh "mvn clean package"
      }
    }
    stage('Archive artifacts'){
      steps{
        archiveArtifacts artifacts:'target/*.war'
      }
    }
    stage('Deploy to Tomcat Server'){
      steps{
        deploy adapters: [tomcat9(credentialsId: 'admin', path: '', url: 'http://localhost:8081/')], contextPath: null, war: '**/*.war'
      }
    }
  }
}
      
    
    
      
    
