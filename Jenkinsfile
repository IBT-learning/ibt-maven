pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('testing') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Git Checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/jan2024franklin']], extensions: [], userRemoteConfigs: [[credentialsId: 'franklin-ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'

            }
        }
    }
}
