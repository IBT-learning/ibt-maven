pipeline {
    agent any
    parameters {
        string(name:'Branch', defaultValue:'main', description:'enter branch to build')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('hi') {
            steps {
                echo 'Hi'
            }
        }
        stage('Git checkout') {
            steps {
                echo 'Hi this is my first pipeline job'
                git branch: 'feature_gunjan', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
         stage('GItSCM') {
                    steps {
                        echo 'trying gitscm to hook logs'
                        echo 'trying gitSCM poll'
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