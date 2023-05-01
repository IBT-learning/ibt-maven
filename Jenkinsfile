pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('test') {
            steps {
                echo 'test'
            }
        }
         stage('yellow') {
            steps {
                 echo 'yellow'
            }
        }
        stage('testing jenkins oncemore') {
                     steps {
                          echo 'testing jenkinsfile oncemore'
                     }
                 }stage('Git checkout') {
                                       steps {
                                            checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_sullivan']], extensions: [], userRemoteConfigs: [[credentialsId: 'IBT-GitHub', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                                            sh 'ls -lrt'

                                       }
                                   }






    }
}