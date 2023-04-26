pipeline {
    agent any
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