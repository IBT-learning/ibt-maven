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
                echo 'Hello World'
            }
        } //stage 2
        stage('Download from Git'){
         steps{
           git branch: 'feature_sagardhungel', credentialsId: 'Github_cred_sagar', url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
      } //stage 3
    } // stages
} //pipeline
