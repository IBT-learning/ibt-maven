pipeline {
    agent any
    parameters {
        string(name:"Branch_Name", defaultValue: "main", description: "Enter branch to build")
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')

    }
    environment{
        version = '1.3.0'
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
        stage('list choice') {
            steps {
               echo "Choice: ${params.CHOICES}"
            }
        }
       stage('run on condition'){
            when {
                expression {
                    env.BRANCH_NAME =='main'
                }
            }
            steps{
                echo "running on main branch"
            }
       }
        stage('test') {
            steps {
                echo 'testing'
                echo "${env.version}"
                sh 'echo $version'
            }
        }
    }
    post {
      always {
          echo 'I will always say Hello again!'
      }
    }
}