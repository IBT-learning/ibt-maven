pipeline {
    agent any

    environment {
            version = "1.5"
            db_name = "ibt_db"
        }

    parameters{ choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
    string(name: 'Branch_Name', defaultValue: 'main', description: 'enter branch to build')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('Holla') {
             steps {
                echo 'Holla World'
             }
         }
         stage('git checkout') {
                      steps {
                         git branch: 'main', changelog: false, credentialsId: 'git_password', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                      }
                  }
         stage('list files') {
                               steps {
                               sh 'ls -lrt'
                               }
                           }
         stage('env variables') {
             steps{
                 sh 'echo $version '
                 echo "${env.version}"
                 echo "${env.db_name}"

                 script {
                     print env.version
                 }
    }
}