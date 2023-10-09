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
         stage('Git checkout'){
            steps{
                git branch: 'feature_gunj', changelog: false, credentialsId: 'GitHub_user_cred_gunjan', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
         }
         stage('list all my files') {
            steps{
                sh 'ls -lrt'
            }
         }
    }
}