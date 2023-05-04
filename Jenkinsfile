pipeline {
    environment{
    version = '1.3.0'
    }
    tools {
        maven 'maven_3.8'
    }
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('Hi') {
            steps {
                echo 'Hi'
                echo "${env.version}"
            }
        }
          stage('test') {
            steps {
                echo 'test'
            }
        }
         stage('testing jenkinsfile') {
         when{
             expression{
                 env.BRANCH_NAME=='main'
             }
         }
                    steps {
                        echo 'testing jenkinsfile'
                    }
                }
         stage("git checkout") {
             steps{
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_belirta']], extensions: [], userRemoteConfigs: [[credentialsId: 'beli-git', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
                sh 'echo $Branch_Name $CHOICES'
                sh 'echo trying hooks'
           }
         }
         stage('testing hooks') {
          environment{
                 version2 = '1.5.0'
             }
             steps {
                 echo 'hook tested success'
                 echo "${env.version2}"
             }
         }
         stage('mvn version') {
                     steps {
                         sh 'mvn --version'
                     }
                }
    }
    post{
        always{
            emailext body: 'text', subject: 'text', to: 'dinayenbelirta@gmail.com'
            echo "Build successful"
        }
    }
}