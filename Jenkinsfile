pipeline{
    tools{        
        maven 'my_maven'
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
                  sh 'mvn compile'
              }
          }
          stage('CodeReview'){
              agent any
              steps{
                  sh 'mvn pmd:pmd'
              }
          }
          stage('UnitTest'){
              agent {label 'linux_slave'}
              steps{
                  git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
                  sh 'mvn test'
              }
              
          }          
          stage('Package'){
              agent any
              steps{
                  sh 'mvn package'
              }
          }
      }
}
