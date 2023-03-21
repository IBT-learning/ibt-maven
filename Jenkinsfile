pipeline {
    agent any
    parameters {
        string(name:'Branch', defaultValue:'main', description:'enter branch to build')
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('hi') {
            when {
                expression {
                    env.BRANCH_NAME == 'feature_gunjan'
                }
            }
            steps {
                echo 'Hi'
            }
        }
        stage('Git checkout') {
            steps {
                echo 'Hi this is my first pipeline job'
                git branch: '${Branch}', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
         stage('GItSCM') {
         environment{
                 version='1.2'
             }
                    steps {
                        echo 'trying gitscm to hook logs'
                        echo "${env.version}"
                        sh "echo $version"
                        script {
                            print env.version
                         }
                    }
                }
    }
}