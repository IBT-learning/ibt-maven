pipeline{
    agent any

    stages{
        stage('Hello') {
            steps {
                echo 'hello'
                }
        }
        stage('hi') {
                    steps {
                        echo 'hi'
                        }
                }
        stage('Git checkout')
            steps {
                git branch: 'feature_iyke', changelog: false, credentialsId: 'Github_user_cred_iyke', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                }
           }
    }
}