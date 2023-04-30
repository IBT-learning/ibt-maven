pipeline {
    agent any
    parameters{
        string(name: 'Branch_Name', defaultValue: 'main', description: 'Enter the branch to checkout')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi'
            }
        }
         stage('Hi test') {
            steps {
                echo 'Hi testing Jenkins'
            }
        }
        stage('Jenkinsfile test') {
             steps {
                 echo 'Jenkinsfile test'
                    }
                }
        stage('Git checkout') {
            steps {
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
                sh 'echo $Branch_Name $CHOICES'
            }
        }
         stage('Testing hooks') {
                     steps {
                         echo 'Testing hooks - **SUCCESS**'
                            }
                        }
    }
}
