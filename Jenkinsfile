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
                echo 'Hello this is abraham'
            }
        }
        stage('Hiiii') {
                    steps {
                        echo 'this is running from github'
                    }
                }
           stage('git checkout') {
           steps {
           git branch: 'feature_abem', changelog: false, credentialsId: 'Git_Credentials_abe', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
           }
           }
           stage('list files') {
           steps {
           sh '''
           ls -lrt
           pwd
           who
           '''
           }
           }
    }
}