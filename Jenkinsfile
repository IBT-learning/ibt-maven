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
                echo 'Hi'
            }
        }
        stage('Git checkout') {
            steps {
                echo 'Hi this is my first pipeline job'
                git branch: 'feature_gunjan', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }
}