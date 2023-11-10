pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi this is Chinwe'
            }
        }
        stage('trying jenkinsfile'){
            steps{
                 echo 'this is running from github'
            }
        }
        stage('git checkout'){
             steps{
                  git branch: 'feature_chinwe', changelog: false, credentialsId: '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', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
         stage('list files'){
         steps{
              sh '''
              pwd
              who
              '''
          }
         }
        }
    }


