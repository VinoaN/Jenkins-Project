pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven-3.8.3'
  }
  stages{
    stage("Cleanup Workspace"){
      steps{
        cleanWs()
      }
    }
    stage("Checkout from SCM"){
      steps{
        git branch : 'main' , credentialsId: 'github' , url : 'https://github.com/VinoaN/Jenkins-Project'
      }
    }
    stage("Build Application"){
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
