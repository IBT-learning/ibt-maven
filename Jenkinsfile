pipeline{
    agent any

    stages {
        stage('Git checkout') {
                    steps{
                        checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_nnamdi']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-ID', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                        sh 'ls -lrt'
                    }
        }
    }