pipeline {
     agent any

parameters {
      string (name: 'Branch_Name' , defaultValue: 'main' , description: 'enter the branch to build')

}
     stages {
          stage('hello world') {
           steps {
           echo "hello world"
         }
       }
   stage('hello ') {
           steps {
           echo "hello"
         }
       }
     stage('Git checkout'){
       steps{
       git branch: '$Branch_Name', changelog: false, credentialsId: 'Github_user_cred_winfred', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'

        }

      }
      stage('list all files') {
      steps{
      bat 'dir'
      }

      }

    }

}