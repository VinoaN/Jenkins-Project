pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
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
        sh ' ' '
        
      }
      
    }
    stage("Test Application"){
      steps{
        sh 'mvn test'
        
      }
      
    }
}
}
