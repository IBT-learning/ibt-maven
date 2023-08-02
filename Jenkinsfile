pipeline {
    agent any
    tools { maven  'maven_3.8' }
    environment {
        version = '1.3.0'
        run = 'true'
    }
    parameters {
        string(name:'Branch_Name', defaultValue: 'main', description: 'enter branch name to build')
    }

    stages {
        stage('Hello') {
          steps {
                echo 'Hello World'
            }
        }
        stage('hi') {
            steps {
                echo 'hi'
            }
        }
       stage('Git Checkout') {
          steps{
            checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
          }
       }
       stage('List files'){
       when {
            expression{
                env.BRANCH_NAME == 'main'
            }
       }
        steps{
            sh 'ls'
        }
       }
        stage('invoke python'){
               steps{
                   sh 'pwd'
               }
              }
        stage('invoke maven'){
                       steps {
                           sh 'mvn --version'
                       }
                     }
         stage('test stage') {
            steps {
                sh 'echo hello'
                echo "${env.version}"
                echo "${env.run}"
                sh 'echo $version'
                script {
                    print env.version
                }
            }
         }
    }
    post {
        always {
            echo "hi i am going to run everytime"
        }
    }
}