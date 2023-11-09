pipeline {
    agent any
          parameters {
          string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'which branch to build on')
          choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose your number')
          }


    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hello this is tojja'
            }
        }
        stage('Hiiii') {
                    steps {
                        echo 'this is running from github'
                    }
                }
           stage('git checkout') {
           steps {
           git branch: '$BRANCH_NAME', changelog: false, credentialsId: 'git_credentials_tojja', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
           }
           }
         stage('list files') {
                    steps {
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