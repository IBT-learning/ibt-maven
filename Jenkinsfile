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
                echo 'Hi Mom'
            }
        }
        stage('Howdy') {
            steps {
                echo 'Howdy'
            }
        }
        stage('git checkout') {
            steps {
                git branch: 'wendy-feature', changelog: false, credentialsId: 'git_creds_wendy', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('list files') {
            steps{
                //sh 'ls -lrt' //mac-unix
                 bat 'dir'
            }
        }
    }

}