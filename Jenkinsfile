pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
    stage("Cleanup Workspace"){
      steps{
        cleanWs()
      }
    }
    stage("Checkout from SCM GIT"){
      steps{
        git branch : 'main' , credentialsId: 'github' , url : 'https://github.com/VinoaN/Jenkins-Project'
      }
    }
    stage("Build Application using Maven"){
      steps{
        sh 'mvn clean package'
        
      }
      
    }
    stage("Test Application"){
      steps{
        sh 'mvn test'
        
      }
      
    }
}
}
