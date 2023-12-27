pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Download from Git') {
                    steps {
                        git branch: 'main', changelog: false, credentialsId: 'GitHub_cred_rudwan', poll: false, url: 'https://github.com/rudwan7/demo-nov.git'
                    }
                }
    }
}