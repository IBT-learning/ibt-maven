pipeline {
    agent any
    parameters{
      string(name:'Branch_Name', defaultValue:'main', description:'enter the branch to checkout')
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
          stage('test') {
            steps {
                echo 'test'
            }
        }
         stage('testing jenkinsfile') {
                    steps {
                        echo 'testing jenkinsfile'
                    }
                }
         stage("git checkout") {
             steps{
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_belirta']], extensions: [], userRemoteConfigs: [[credentialsId: 'beli-git', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
           }
         }
    }
}