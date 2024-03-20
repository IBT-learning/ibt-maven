pipeline {
    agent any

    parameters {
       string(name: 'Branch_name', defaultValue: 'main', description: 'Enter branch to build')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            } // step
        } // stage1
        stage('Hi') {
            steps {
                echo 'Hi this is Kingsley'
            } // step
        }// stage2
        stage('Github download') {
            steps {
                git branch: '$Branch_name', credentialsId: 'kingsley_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }

        } //stage3
        stage ('List Repo contents') {
            steps {
                sh 'ls -lrt'
            } //step

        } //stage4
    } // end of stages
} // end of pipeline
