pipeline {

    environment{
        version = '1.25.0'
    }

    tools{
        maven 'maven_3.8'
    }

    agent any

    parameters{
        string(name:'Branch_Name', defaultValue:'feature-irinamm', description:'Enter the branch to checkout')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
    }

    stages {

        stage('Hello') {
            steps {
                echo 'Hello World'
                echo env.BUILD_NUMBER
                echo "${env.version}"
            }
        }

        stage('Testing jenkinsfile') {
            when{
                expression{
                    env.BRANCH_NAME == 'feature-irinamm'
                }
            }
            steps {
                echo 'jenkinsfile'
            }
        }

        stage('Good-bye') {
            steps {
                echo 'Good-bye'
            }
        }

        stage('Git checkout') {
            steps{
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature-irinamm']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
                sh 'echo $Branch_Name $CHOICES'
            }
        }

        stage('testing hook') {
            environment{
                version2 = '1.25.0'
            }
            steps {
                echo 'hook tested successfully'
                echo "${env.version2}"
            }
        }

        stage('mvn version') {
             steps {
                sh 'mvn --version'
             }
        }

        stage('script') {
             steps {
                echo 'Script starting'

                script{
                    def fruits = ['apple', 'kiwi', 'peach']
                    for (int i = 0; i < fruits.size(); i++){
                        echo "The current item is ${fruits[i]}"
                    }
                }


                echo 'Script ends'
             }
        }

    }

    post{
        always{
            emailext body: 'test', subject: 'pipeline_git test', to: 'yrenamm@gmail.com'
        }

    }

}
