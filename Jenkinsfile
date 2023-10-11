pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo "hello"
            }
        }
        stage('hi') {
            steps {
                echo "hi"
            }
        }
        stage('Git Checkout') {
            steps {
                git branch: 'feature_makeda', changelog: false, credentialsId: 'GitHub_user_cred_makeda', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }
}