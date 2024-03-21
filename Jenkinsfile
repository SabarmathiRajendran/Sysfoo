pipeline {
  agent any
  stages{
    stage('Build'){
      steps{ 
        bat "mvn clean package"
      }
    }
    stage('Archive artifacts'){
      steps{
        archiveArtifacts artifacts:'target/*.war'
      }
    }
  }
}
      
    
    
      
    
