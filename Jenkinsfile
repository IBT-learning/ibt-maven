pipeline {
    agent any
    parameters {
        string(name:'Branch', defaultValue:'main', description:'enter branch to build')
    }
    environment{
        Message="Jan26_Cohort"
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo "${env.Message}"
            }
        }
         stage('hi') {
            steps {
                echo 'Hi'
                echo "${env.Message}"
            }
        }
        stage('Git checkout') {
            steps {
                echo 'Hi this is my first pipeline job'
                git branch: '${Branch}', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
         stage('GItSCM') {
                    steps {
                        echo 'trying gitscm to hook logs'
                        echo 'trying gitSCM poll'
                        echo "${env.Message}"
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