pipeline {
    agent any
parameters{
    string(name:'Branch_Name', defaultValue:'main', description:'Enter the branch to build')
}
environment{
    version='1.0.0'
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
        stage('working from github'){
            steps{
                sh "pwd"
            }
        }
        stage('get branchName'){
            steps{
                echo "${params.Branch_Name}"
            }
        }
        stage('git checkout')
        {
            steps{
                checkout scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
            }
        }
         stage('list files'){
            steps{
                sh 'ls'
             }
        }
       stage('checking condition'){
        when{
          expression{
            env.BRANCH_NAME=='main'
          }
        }
        steps{
             echo "i am ruuning since the condition is met"
        }
       }
       stage('variables'){
               steps{
                   sh 'echo "$version" '
                   echo "${env.version}"
                   script{
                       print env.version
                   }
               }
              }
    stage('testing webhook'){
        steps{
            echo "i am running from git push"
        }
    }
  }
    post{
                    always{
                        echo "i will run everytime"
                    }
                }

}