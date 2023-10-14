pipeline {
    agent any
    parameters{
        string(name: 'branch_name', defaultValue: 'main', description: 'enter the branch to build')
    }

    environment{
        version = '1.3.2'
    }
    stages{
        stage('Hello') {
            steps{
                echo "hello"
            }
        }
         stage('Git checkout') {
                    steps{
                        git branch: '$branch_name', credentialsId: 'mvn_user_credential_github', url: 'https://github.com/IBT-learning/ibt-maven.git'
                    }
                }
                stage('list my files'){
                     when{
                         expression{
                             '$branch_name' == 'main'
                             }
                         }
                    steps{
                        sh 'ls'
                    }
                }
                stage('list environment vers'){
                    steps{
                    sh 'echo "${env.version}" '
                    sh 'echo $version'

                    script{
                        print env.version

                    }

                }

         }
    }
}