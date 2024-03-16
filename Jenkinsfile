pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('hi') {
            steps {
                echo 'hi this is anna'
            } //step
        } //stage2
        stage( ' Github download ') {
         step{
             git branch: 'jan2024_bagul', credentialsId: 'bagul_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
             }
         } stage3
         stage ('List Repo contents')  {
         step{
              sh 'ls -lrt'
              }
    } //  end of stages
} //end of pipeline