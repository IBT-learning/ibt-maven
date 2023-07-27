pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('firstline') {
            steps{
                echo 'We are testing maven pipeline job'
            }
        }
        stage('secondline') {
            steps {
                echo 'I am a master in Devops engineering'
                bat 'dir'
            }
        }
    }
}