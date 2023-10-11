pipeline {
    agent any

    parameters {
        string (name: 'Branch_Name' , defaultValue: 'master' , description: 'enter the branch to build')
    }

    environment{
        version = '1.3.0'
    }

    stages {
        stage ('Hello') {
            steps {
                echo "hello"
            }
        }
                stage ('Hi') {
                    steps {
                        echo "hi"
                    }
                }
        stage('Git checkout'){
            steps{
                git branch: '$Branch_Name' , changelog: false, credentialsId: 'Github_user_cred_houdy', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('list all my files') {
           when {
                expression{
                '$Branch_Name'=='master'
                }
           }
            steps{
               bat 'dir'
            }
        }
        stage('list environment vars'){
            steps{
                bat 'echo ${env.version}'
                bat 'echo $version'
                bat '''
                dir
                cd src
                ls-lrt
                '''
                script{
                    print env.version
                }
            }
        }
    }
}