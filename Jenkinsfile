pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }//stage1
        stage('Name') {
            steps {
                echo 'this is Shiney'
            }
        }//stage2
        stage('Github download') {
            steps {
                   git branch: 'jan2024-shiney ', credentialsId: 'shiney495_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
         }//stage3
    }//endofstages
}//endofpipeline
