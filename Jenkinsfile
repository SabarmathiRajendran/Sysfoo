pipeline {
  agent any
  
  stages{
    stage('Checkout Code'){
      steps{
        checkout scm
      }
    }
    stage('Build'){
      steps{ 
        bat "mvn clean install -Dmaven.test.skip=true"
      }
    }
    stage('Archive artifacts'){
      steps{
        archiveArtifacts artifacts:'target/*.war'
      }
    }
    stage('Deployment'){
      steps{
        deploy adapters: [apache-tomcat-9.0.86:(url:'http://localhost:8081/', credentialsId: 'admin')]
        war:'target/*.war'
        contextPath: 'app'
      }
    }
    stage('Notification'){
      steps{
        emailext(
          subject:'Job Completed',
          body: "Jenkins pipeline job for maven build completed",
          to: 'sabarraju@gmail.com'
        )
      }
    }
      
    
    
      
    
