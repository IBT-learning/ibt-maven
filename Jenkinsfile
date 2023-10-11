pipeline {
    agent any

    stages {
        stage ('Hello') {
            steps {
                echo "hello"
            }
        }
                stage ('Hi') {
                    steps {
                        echo "hi"
                    }
                }
        stage('Git checkout'){
            steps{
                git branch: 'feature_houdy', changelog: false, credentialsId: 'Github_user_cred_houdy', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }
}