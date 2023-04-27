pipeline {
    agent any
    tool{
        maven 'maven_3.8'
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
                      echo 'jenkinsfile'
                   }
               }
        stage('Git checkout') {
            steps{
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_nnamdi']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                echo 'checking out'
                sh 'ls -lrt'
            }
        }
        stage('mvn version') {
            step{
                sh 'mvn --version'
            }
        }
    }
}
