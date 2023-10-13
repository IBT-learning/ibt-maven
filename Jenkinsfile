pipeline {
    agent any

    stages{
        stage('Hello') {
            steps{
                echo "hello"
            }
        }
         stage('Git checkout') {
                    steps{
                        git branch: 'feature_abreham', credentialsId: 'mvn_user_credential_github', url: 'https://github.com/IBT-learning/ibt-maven.git'
                    }
                }
                stage('list my files'){
                    steps{
                        bat 'dir'
                    }
                }
    }
}