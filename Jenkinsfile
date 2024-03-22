pipeline {
    agent any

    parameters {
        string(name: 'Branch_name', defaultValue: 'main',description: 'Enter branch to build')
    }


    stages {
        stage('Hello-step1') {
            steps {
                echo 'Hello World'
            }
        }//stage1
        stage('Name-step2') {
            steps {
                echo 'this is Shiney'
            }
        }//stage2
        stage('Github download-step3') {
            steps {
                   git branch: '$Branch_name', credentialsId: 'shiney495_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
         }//stage3
         stage('Example Deploy-step4'){
         when {
            branch 'main'
         }
            steps{
               echo "Deploying...."
            }
         } //steps4

         stage('windows command-step4'){
               steps {
               bat '''dir
               netstat -noab'''
               }
         }//stage4
         stage("print commands-final?") {
            steps{
            echo '$Branch_name'
            }
         }

    }//endofstages
}//endofpipeline
