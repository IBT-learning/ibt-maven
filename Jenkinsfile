pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        } // stage 1
        stage('Hi') {
            steps {
                echo 'Hello World'
            }
        }// stage 2
        stage('Download from Git'){
        steps{
        git branch: 'main', credentialsId: 'GitHub_cred_Tagne', url: 'https://github.com/christeukam/nov-cohort.git'
             }
        } // stage 3

    } // stages
} // pipeline