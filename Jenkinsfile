pipeline {
 agent any

 stages {
    stage('hello') {
        steps {
            echo "hello world"
        } //step
    } //stage1
    stage('hi') {
        steps {
            echo "hi this is gunjan"
        } //step
    } //stage2
    stage('Github download') {
        steps{
            git branch: 'jan2024_gunjan', credentialsId: 'gunjan_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
    } //stage3
    stage ('List Repo contents ') {
        steps{
            sh 'ls -lrt'
            // bat 'dir' -- for windows
        } //step
    } //stage4
 } // end of stages
} // end of pipeline