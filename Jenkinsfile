pipeline {
    agent any
    parameters{
        string(name:'Branch_Name', defaultValue: 'master',description: 'Enter the branch name')
    }
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
                checkout scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'franklin-ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
                sh 'echo $Branch_Name'

            }
        }
    }
}
