pipeline{
  agent any

parameters {
string(name:"Branch_Name", defaultvalue: "main", description: "Enter branch to built")
}
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
         git branch: '$Branch_Name', changelog: false, credentialsId: 'GitHub_cred_Nasirfaizi', poll: false, url: 'https://github.com/Nasirfaizi/nov-cohort.git'
       }
     } //stage 3
 stage('list files'){
    echo "listing files to verify"
 steps{bat 'dir'

 }
 }
  } //stages
} //pipeline