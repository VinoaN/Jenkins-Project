pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
  }
  stages{
    stage("Cleanup Workspace"){
      steps{
        CleanWs()
      }
    }
    stage("Checkout from SCM"){
      steps{
        git branch : 'main' , credentialsId: 'github' , url : 'https://github.com/VinoaN/Jenkins-Project'
      }
    }
    stage("Build Application"){
      steps{
        sh 'MVN Clean Package'
        
      }
      
    }
    stage("Test Application"){
      steps{
        sh 'MVN test'
        
      }
      
    }
}
}
