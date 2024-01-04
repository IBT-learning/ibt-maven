pipeline{
  agent any

  stages{
  stage('Hello'){
  steps{
      echo "hello"
    }
  } // stage 1
  stage('Hi'){
    steps{
      echo "Hi"
    }
   } //stage 2
   stage('Download from git'){
   steps{
         git branch: 'main', changelog: false, credentialsId: 'GitHub_cred_Nasirfaizi', poll: false, url: 'https://github.com/Nasirfaizi/nov-cohort.git'
       }
     } //stage 3
     stage('List files'){'
 steps{
      bat 'dir'
     }
   }
  } //stages
} //pipeline
