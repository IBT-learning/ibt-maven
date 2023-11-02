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
                echo 'Hello this is tojja'
            }
        }
        stage('Hiiii') {
                    steps {
                        echo 'this is running from github'
                    }
                }
           stage('git checkout') {
           steps {
           git branch: 'feature_tojja', changelog: false, credentialsId: 'git_credentials_tojja', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
           }
           }
    }
}