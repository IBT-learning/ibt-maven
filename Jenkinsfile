pipeline {
    agent any

    parameters {
    string(name:Branch_Name, defaultValue: "main", description:"Enter a branch to build")
    }

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
        git branch: '$Branch_name', credentialsId: 'GitHub_cred_Tagne', url: 'https://github.com/christeukam/nov-cohort.git'
             }
        } // stage 3
        stage('List files'){
                steps{bat 'dir'
             }
        } // stage 4

    }// stages
} // pipeline