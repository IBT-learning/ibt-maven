pipeline {
    agent any
    parameters {
        string(name:"Branch_Name", defaultValue: "main", description: "Enter branch to build")
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
      }

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
                        git branch: '$Branch_Name', changelog: false, credentialsId: 'GitHub_cred_rudwan', poll: false, url: 'https://github.com/rudwan7/demo-nov.git'
                    }
                }
        stage('list files') {
                            steps {
                                sh 'ls -lrt'
                            }
                        }
    }
}