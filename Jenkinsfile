pipeline {
    agent any

    parameters {
        string (name: Branch_Name , defaultValue: main , description: 'enter tne branch to build')
    }

    stages {
        stage('Hello'){
            steps {
                echo "hello"
            }
        }
        stage('Git checkout'){
            steps {
                git branch: $Branch_Name , credentialsId: 'GtiHub_user_cred_franck', url: 'https://github.com/IBT-learning/ibt-maven.git'
                }

        }
        stage('list all my files') {
            steps{
                sh 'ls -lrt'
            }
        }
    }
}