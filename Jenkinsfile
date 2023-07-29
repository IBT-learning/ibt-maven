pipeline {
    agent any
    // string (Name: 'Branch_name', defaultValue: 'main', Description: 'Enter a Branch to build')
    parameters {
        string (name:'Branch_Name', defaultValue:'main', description:'Enter the branch to build')
    }
    environment{
        version='1.0.0'

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
    }
}
