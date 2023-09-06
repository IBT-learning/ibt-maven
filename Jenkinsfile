pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

     stage('Hi Five') {
                 steps {
                     echo 'Hi Five'
                 }
             }

              stage('trial-1') {
                              steps {
                                  echo 'trial-1'
                              }
                          }
           stage('trial-2') {
                           steps {
                               echo 'trial-2'
                           }
                       }
                        stage('trial-3') {
                           steps {
                               echo 'trial-3'
                           }
                       }
                        stage('trial-4') {
                           steps {
                               echo 'trial-4'
                           }
                       }
                       stage('exp') {
                                                  steps {
                                                      echo 'exp'
                                                  }
                                              }
         stage('git checkout') {
              steps {
             git branch: 'main', changelog: false, credentialsId: 'GGD', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                }
             }
             stage('list files'){
             steps{
             bat 'dir'} //for window
             //sh 'ls -lrt' for mac or linux
    }
}
    }
}