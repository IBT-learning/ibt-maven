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
                echo 'Hi this is my first pipeline job'
            }
        }
           stage('Git checkout') {
            steps {
                echo 'Hi this is my first pipeline job'
                git branch: 'patdada', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
         stage('GitSCM') {
                    steps {
                        echo 'Trying gitscm on jenkinsfile'
                    }
                }
    }
}