pipeline {
    agent any

    parameters {
        string (name: 'Branch_Name' , defaultValue: 'main' , description: 'enter the branch to build')
    }

    environment{
        version = '1.3.0'
    }

    stages {
        stage('Hello'){
            steps {
                echo "hello"
            }
        }
        stage('Git checkout'){
            steps {
                git branch: '$Branch_Name' , credentialsId: 'GtiHub_user_cred_franck', url: 'https://github.com/IBT-learning/ibt-maven.git'
                }

        }
        stage('list all my files') {
            when{
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
                sh 'echo "${env. version}" '
                sh 'echo $version'
                script{
                    print env.version
                }
            }
        }
    }
}