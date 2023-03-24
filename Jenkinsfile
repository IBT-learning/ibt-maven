 pipeline {
     agent any
     parameter {
        string(name: 'Branch', defaultValue:'main', description: 'Enter branch to build')
     }
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
         stage('WEBHOOK') {
               steps {
                   echo 'Im tryin this to see if webhook is working.'
               }
          }
         stage('commands & code') {
             steps {
                 echo 'Im trying some commands.'
                 sh 'pwd'
                 sh 'who'
                 script {
                    def version = '1.0.1'
                    echo "${version}"
                 }
             }
        }
     }
 }
