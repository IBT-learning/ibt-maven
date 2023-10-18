pipeline {
    agent {label 'UX_IBT'}

    parameters {
        string (name: 'Branch_Name' , defaultValue: 'main' , description: 'enter the branch to build')
    }

    environment{
        version = '1.3.0'
    }

    stages {
        stage('Hello') {
            steps {
                echo "hello"
            }
        }
          stage('hi') {
                    steps {
                        echo "hi"
                    }
                }
         stage('Git checkout'){
            steps{
                  git branch: 'feature-rizme', changelog: false, credentialsId: 'GitHub_user_rizme', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
         }
         stage('list all my files') {
            when {
                expression{
                    '$Branch_Name'=='main'
                }
            }
            steps{
                sh 'ls -lrt'
            }
         }
         stage('list environment vars'){
            steps{
                //sh 'echo "${env.version}" '
                sh 'echo $version'
                sh '''
                    ls -lrt
                    cd src
                    ls -lrt
                '''
                script{
                   print env.version
                }

            }
         }
       stage('checking webhook') {
                           steps {
                               echo "hi from auto run"
                           }
                       }
    }
}