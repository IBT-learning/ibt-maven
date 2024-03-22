pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Name stage') {
            steps {
                echo 'this is uzoma'
            }
        }
        stage('inst stage') {
            steps {
                echo 'this is ibt institute'
            }
        }
        stage ('Github Download') {
           steps{
           git branch: 'feature-uzoma', credentialsId: 'github_creds_uzoma', url: 'https://github.com/IBT-learning/ibt-maven.git'
           }

        }
    }
}//end of pipeline
