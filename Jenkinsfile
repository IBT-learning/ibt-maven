pipeline {
    agent any
    parameters{
        string(name:'Branch_Name', defaultValue:'feature-irinamm', description:'Enter the branch to checkout')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo env.BUILD_NUMBER
            }
        }
        stage('Testing jenkinsfile') {
        when{
            expression{
                env.BRANCH_NAME=='feature-irinamm'
            }
        }
                    steps {
                        echo 'jenkinsfile'
                        echo $env.BRANCH_NAME
                    }
                }
        stage('Good-bye') {
            steps {
                echo 'Good-bye'
            }
        }
        stage('Git checkout') {
            steps{
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature-irinamm']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
                sh 'echo $Branch_Name $CHOICES'
            }
        }
        stage('testing hook') {
              steps {
                echo 'hook tested successfully'
             }
        }

    }
}
