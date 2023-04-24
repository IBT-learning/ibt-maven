pipeline {
    agent any
    parameters{
      string(name:'Branch_Name', defaultValue:'main', description:'Enter the branch to checkout')
      choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
    }
    stages {
        stage('Git checkout') {
                    steps{
                        checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_nnamdi']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-ID', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                        sh 'ls -lrt'
                    }
        }
    }
