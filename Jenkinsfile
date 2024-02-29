pipeline {
    agent any
    parameters{
        string(name:'Branch_Name', defaultValue: 'jan2024franklin',description: 'Enter the branch name')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World  I am here'
            }
        }

        stage('testing') {
            steps {
                // when {
                //     expression {
                //         $Branch_Name =='jan2024franklin'
                      
                      
                //     }
                //   }
            
                echo 'Hello World'
            }
        }
        stage('Git Checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'franklin-ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
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
