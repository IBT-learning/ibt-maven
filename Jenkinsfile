pipeline {
    agent any
parameters{
string(name:'Branch_Name',defaultValue:'main',description:'Enterthe branch to build')
}
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('hi') {
            steps {
                echo 'hi this is ache'
            }
        }
        stage('working from github'){
          steps{
            sh "pwd"
          }
        }
    }
}
