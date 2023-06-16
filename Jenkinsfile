pipeline {
    agent any

    stages {
        stage('Pipeline_with_Git') {
            steps {
                echo 'Hello World from GIT'
            }
        }
        stage('New Stage') {
            steps {
                echo 'New stage has been added'
            }
        }
        stage('Another Stage for testing') {
                    steps {
                        echo 'Another stage'
                    }
                }
        stage ('Git checkout'){
                    steps {
                        checkout scmGit(branches: [[name: '*/feature-Elena']], extensions: [], userRemoteConfigs: [[credentialsId: 'IBT_Elena', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                        sh 'ls -lrt'
                    }
                }

    }
}
