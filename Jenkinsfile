pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Git Checkout') {
            steps {
                git branch: 'feature_koby2', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('Maven') {
            steps {
                sh 'mvn clean'
            }
        }
    }
    post {
        always {
            echo "i will run always"
        }
    }
}
