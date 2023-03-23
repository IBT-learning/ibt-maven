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
           stage('Hi') {
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
        stage('GITSCM') {
           when{
                expression {
                        env.BRANCH_NAME == "main"
                }
               }
                   steps {
                   echo 'trying gitscm to hook logs'
                   echo 'trying gitscm polls'
                   echo "${env.Message}"

                   }
               }
         stage('Build'){
         environment{
          variable="435"
         }
           steps{
                 sh "pwd"
                 sh "who"
                 echo "{env.variable}"
                script{
                  def version = '1.2'
                  echo "${version}"
                }
           }
    post {
        always{
             echo "i will run always"
}
