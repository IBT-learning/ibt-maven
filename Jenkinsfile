pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
       stage('trying jenkinsfile') {
                   steps {
                       echo 'This is running from github'
                   }
               }
                stage('Git checkout') {
                                  steps {
                                      git branch: 'feature_amoo', credentialsId: 'Abdullahi_amoo', url: 'https://github.com/IBT-learning/ibt-maven.git'
                                  }
                              }
                stage(' linux command ') {
                                 steps{
                                        sh 'ls -lrt'
                                 }
                              }
                stage('list files' {
                     steps{
                     sh '''
                     ls -lrt
                     pwd
                     who
                     '''
                     }
                     }
                }
                }

    }

