 pipeline {
     agent any
     parameters {
        string(name:'Branch', defaultValue:'main', description: 'Enter branch to build')
     }
     environment {
        Message = "jan26Cohort"
     }
     stages {
         stage('Hello') {
             steps {
                 echo 'Hello World'
                 echo "${env.Message}"
             }
         }
         stage('Git checkout') {
             steps {
                 git branch: '${Branch}', changelog: false, credentialsId: 'github-jashan', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
             }
         }
         stage('GitSCM') {
             steps {
                 echo 'I not yet trying git scm'
                 echo "${env.Message}"
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
                   echo "${env.Message}"
               }
          }
         stage('commands & code') {
            when{
                expression {
                    env.BRANCH_NAME == "main"
                }
            }
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
