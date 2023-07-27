pipeline {
    agent any
    // string (Name: 'Branch_name', defaultValue: 'main', Description: 'Enter a Branch to build')
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
