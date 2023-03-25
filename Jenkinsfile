pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World this my first pipeline job'
            }
        }
         stage('Hi') {
            steps {
                echo 'Hi World this my first pipeline job'
            }
        }
         stage('Git checkout') {
            steps {
                echo 'Hi World this my first pipeline job'
                git branch: 'feature-omoniyi', credentialsId: 'jenkins', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
      stages('Build'){
         steps{
               sh 'pwd'
               sh 'who'
               script{
                  def version = '1.2'
                  echo "${version}"
               }
         }
      }
    }

}