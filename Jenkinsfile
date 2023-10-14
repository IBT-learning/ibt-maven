pipeline {
    agent any

    stages {
        stage('Hello'){
            steps {
                echo "hello"
            }
        }
        stage('Hi'){
                    steps {
                        echo "Hi"
                    }
                }
        stage ('Git checkout') {
            steps{
                git branch: 'feature-conrad', changelog: false, credentialsId: 'Github_user_cred_ccjacobs14', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }
}