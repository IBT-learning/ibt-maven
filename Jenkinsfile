pipeline {
    agent {label 'UX_IBT'}

    parameters {
        string (name: 'Branch_Name' , defaultValue: 'main', description: 'enter the branch to build')
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
        stage('Hi'){
                    steps {
                        echo "Hi"
                    }
                }
        stage ('Git checkout') {
            steps{
                git branch: '$Branch_Name', changelog: false, credentialsId: 'Github_user_cred_ccjacobs14', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('list all my files') {
            when {
                expression{
                    '$Branch_Name'=='main'
                }
            }
            steps{
            sh 'ls'
            }
        }
        stage('list environment var'){
            steps{
                //bat 'echo "%{env.version}"'
                sh 'echo %version%'
                sh '''
                    ls
                    cd src
                    ls
                '''
                script{
                    print env.version
                }

            }
        }
        stage('checking webhook'){
                            steps {
                                echo "hi from auto run"
                            }
                        }
    }
}