pipeline {
parameters {
    string(name:'Branch_name', defaultValue:'main', description:'enter your branch name')
}
    agent {
            docker {
                image 'maven:3.9.4-eclipse-temurin-17-alpine'
                args '-v /root/.m2:/root/.m2'
            }
        }
    stages {
        stage ('hello') {
            steps {
                echo "hello world"
            }
        }
         stage ('hi') {
             steps {
                  echo "hi"
             }
         }
         stage ('windows bash cmd') {
            steps {
                sh "pwd"
            }
         }
         stage ('get branchname') {
            steps {
                echo "${params.$Branch_name}"
            }
         }
         stage ('git checkout') {
            steps {
                git branch: 'feature-laura',
                    credentialsId: 'git_credential_laura',
                    url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
         }
         stage ('build') {
            steps {
                sh 'mvn validate'
                sh 'mvn compile'
                sh 'mvn package'
            }
         }
         stage ('checking condition') {
            when {
                expression {
                    env.Branch_name=='feature-laura'
                }
            }
         steps {
             echo "I will run if condition is met"
            }
         }
         stage('nexus credentials') {
            steps {
                credentialsId: 'laura-nexus'
                url: 'http://192.168.1.161:8081/'
                }
            }
         stage('deplo'){
            steps {
                sh 'mvn deploy'
            }
         }
    }
}
