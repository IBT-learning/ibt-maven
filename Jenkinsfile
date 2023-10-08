pipeline {
    agent any
    parameters {
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'make a selection')
        string(name: 'Branch_Name', defaultValue: 'main', description:'enter branch to build')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi Mom'
            }
        }
        stage('Howdy') {
            steps {
                echo 'Howdy'
            }
        }
        stage('git checkout') {
            steps {
                git branch: 'main', changelog: false, credentialsId: 'git_creds_wendy', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('list files') {
            steps{
                tool name: 'maven_3.9', type: 'maven'
                //sh 'ls -lrt' //mac-unix
                 bat 'dir'
            }
        }
    }

}