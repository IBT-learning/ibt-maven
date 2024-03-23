pipeline {
    agent any
parameters {
    string(name: 'branch_name', defaultValue: 'feature-uzoma', description: 'Enter branch to build')
    choice(name: 'CHOICE', choices: ['Python3', 'Go', 'Ruby'], description: 'Enter Technology')
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
        stage ('Print command') {
           steps {
               echo '$CHOICE'
               echo "Choice: ${params.CHOICE}"
           }
        }
    }
}//end of pipeline
