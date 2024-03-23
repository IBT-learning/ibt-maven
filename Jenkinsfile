pipeline {
    agent any
parameters {
    string(name: 'branch_name', defaultValue: 'feature-uzoma', description: 'Enter branch to build')
}

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Name stage') {
            steps {
                echo 'this is uzoma'
            }
        }
        stage('inst stage') {
            steps {
                echo 'this is ibt institute'
            }
        }
        stage ('Github Download') {
           steps{
           git branch: '$branch_name', credentialsId: 'github_creds_uzoma', url: 'https://github.com/IBT-learning/ibt-maven.git'
           }

        }
        stage ('list Repo content'){
          steps {
          sh 'ls -lart'

          }
        }
    }
}//end of pipeline
