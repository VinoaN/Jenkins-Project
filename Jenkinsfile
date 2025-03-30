pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven4'
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
        sh 'mvn clean package -X'
        sh 'mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DgroupId=com.teamtreehouse.com -DartifactId=file-spy -B'
        
      }
      
    }
    stage("Test Application"){
      steps{
        sh 'mvn test'
        
      }
      
    }
}
}
