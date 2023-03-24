 pipeline {
     agent any

     stages {
         stage('Hello') {
             steps {
                 echo 'Hello World'
             }
         }
         stage('Git checkout') {
             steps {
                 git branch: 'feature-moses', changelog: false, credentialsId: 'github-jashan', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
             }
         }
         stage('GitSCM') {
             steps {
                 echo 'I not yet trying git scm'
             }
         }
         stage('correct - GitSCM') {
              steps {
                  echo 'I did try git scm. And it is working'
              }
         }
     }
 }
