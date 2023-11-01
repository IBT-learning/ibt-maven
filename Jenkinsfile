pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'which branch to build on')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose your number ')
      }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi this is Gunjan'
            }
        }
        stage('trying jeninsfile'){
            steps{
                echo "this is running from github"
            }
        }
        stage('Git checkout'){
            steps{
                git branch: '$BRANCH_NAME', changelog: false, credentialsId: 'ibt', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                sh 'ls -lrt'
            }
        }
        stage('list files'){
            steps{
                sh '''
                ls -lrt
                pwd
                who
                '''
            }
        }

       stage('parameter'){
        steps{
            sh 'echo $CHOICES'
        }
       }
    }
}