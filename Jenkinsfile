pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        } //stage 1
        stage('Hi') {
            steps {
                echo 'Hi World'
            }
        } //stage2
        stage('download from git'){
            steps{
                git branch: 'feature-ramin', credentialsId: 'Github_Cred_Ramin', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    } // stages
} // End pipeline