pipeline {
    agent any
parameters{
    string(name:'Branch_Name', defaultValue:'main', description:'Enter the branch to build')
}

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