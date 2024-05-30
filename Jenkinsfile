pipeline{
    tools{        
        maven 'my_maven'
        jdk 'my_jdk'
    }
    agent none
      stages{
          stage('Checkout'){
              agent any
              steps{
              git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
              }
          }
          stage('Compile'){
              agent any
              steps{
                  bat 'mvn compile'
              }
          }         
          stage('UnitTest'){
              agent any
              steps{                  
                  bat 'mvn test'
              }              
          }          
          stage('Package'){
              agent any
              steps{
                  bat 'mvn package'
              }
          }
      }
}
