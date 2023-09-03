pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('Holla') {
             steps {
                echo 'Holla World'
             }
         }
         stage('git checkout') {
                      steps {
                         git branch: 'main', changelog: false, credentialsId: 'git_password', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                      }
                  }
         stage('list files') {
                      steps {
                      bat 'dir'
    }
}