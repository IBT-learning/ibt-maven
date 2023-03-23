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
                echo 'Hi this is my first pipeline job'
            }
        }
        stage('Git checkout') {
            steps {
                echo 'Hi this is my first pipeline job'
                git branch: 'patdada', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('GITSCM') {
                   steps {
                   echo 'trying gitscm to hook logs'
                   echo 'trying gitscm polls'

                   }
               }
         stage('Build'){
           steps{
                 sh "pwd"
                 sh "who"
                script{
                  def version = '1.2'
                  echo "${version}"
                }
           }
        }

     }
}