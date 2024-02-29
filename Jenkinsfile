pipeline {
    agent any
    parameters{
        //string(name:'Branch_Name', defaultValue: 'master',description: 'Enter the branch name')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World  I am here'
            }
        }

        stage('testing') {
            steps {
                when {
                    expression {
                      env.BRANCH_NAME=='jan2024franklin'
                      
                    }
                  }
            
                echo 'Hello World'
            }
        }
        stage('Git Checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/jan2024franklin']], extensions: [], userRemoteConfigs: [[credentialsId: 'franklin-ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
                sh 'echo $Branch_Name'

            }
        }
        stage('check hookcc'){
                    steps{

                        sh 'ls -lrt'
                        sh 'echo $Branch_Name'

                    }
                }
    }
}
