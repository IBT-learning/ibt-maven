   pipeline {
      agent any
       parameters{
            string(name: 'Branch_Name', defaultValue:'main',description: 'Enter the branch to build')
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
          stage('firstline'){
               steps{
                   echo 'We are testing maven pipeline job'
               }
          }
          stage('displaying this message'){
              steps{
                  echo 'I am a master in Devops engineering'
              }
          }
          stage('get branchname'){
            steps{
              echo "${params.$Branch_Name}"
            }
          }
          stage('git checkout')  {
            steps{
            checkout scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: '1e7e3334-4478-4db6-92bd-fccd4de8a751', url: 'https://github.com/IBT-learning/ibt-maven.git']])
            }
          }
          stage('checking condition'){
          when{
            expression{
              env.BRANCH_NAME=='main'
            }
          }
               steps{
                echo 'i am trying a condition'
               }
          }
          stage('variables'){
            steps{
              echo '${env.version}'
              script{
              print env.version
              }
            }
          }
       }
   }































