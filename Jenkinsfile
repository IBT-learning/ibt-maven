pipeline {
     agent any


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
       git branch: 'feature-winfred', changelog: false, credentialsId: 'Github_user_cred_winfred', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'

        }

      }

    }

}