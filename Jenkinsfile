pipeline {
   agent any
   parameters{
        string(name: 'Branch_Name', defaultValue:'main', description:'enter the value to checkout')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('test') {
            steps {
                echo 'test'
            }
        }
         stage('yellow') {
            steps {
                 echo 'yellow'
            }
        }
        stage('testing Jenkins once more') {
                     steps {
                          echo 'testing Jenkins file once more'
                     }
                 }
        stage('Git checkout') {
               steps {
                    checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'IBT-GitHub', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                                            sh 'dir'
                                            sh 'echo $Branch_Name $CHOICES'
                }
                      {
        stage('testing Ci pipeline') {
               steps {
                     echo 'testing Ci pipeline'
                                 }
                             }

                 }






       }
    }
}