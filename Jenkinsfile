pipeline {
    agent any


    parameters {
        string (name: 'Branch_Name', defaultValue: 'main' , description: 'enter the branch to build')
    }
    environment {
        version = '1.3.0'
    }

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
        stage('Git Checkout') {
            steps {
                git branch: '$Branch_Name', changelog: false, credentialsId: 'GitHub_user_cred_makeda', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('list all my files') {
           when {
              expression{
                 '$Branch_Name'=='main'
              }
           }
             steps {
                bat 'dir'
            }
        }
        stage('list environment vars'){
           steps{
             //bat 'echo "${env.version}" '
             sh 'echo $version'
             sh '''
                -ls lrt
                cd src
                -ls lrt
             '''
             script{
               print env. version
             }
           }
        }
    }
}