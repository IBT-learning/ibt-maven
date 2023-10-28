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
                echo 'Hi this is Gunjan'
            }
        }
        stage('trying jeninsfile'){
            steps{
                echo "this is running from github"
            }
        }
        stage('Git checkout'){
            steps{
                git branch: 'feature_gunjanm', changelog: false, credentialsId: 'ibt', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }
}