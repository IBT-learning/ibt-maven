pipeline {
    agent any
    // string (Name: 'Branch_name', defaultValue: 'main', Description: 'Enter a Branch to build')
    parameters {
        string (name:'Branch_Name', defaultValue:'main', description:'Enter the branch to build')
    }
    //environment{
    //    version='1.0.0'

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
       stage('hi') {
            steps {
                echo 'hi'
            }
        }
        stage('working from github'){
            steps{
                sh "pwd"
            }
        }
        stage('get branchName'){
            steps{
                   echo "${params.Branch_Name}"
                    }
                }
        stage('git checkout')
                {
           steps{
                   checkout scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                    }
                }
    }
}
