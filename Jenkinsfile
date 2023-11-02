pipeline {
    agent any
    parameters { string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'which branch to build on')
                 choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose your number')
                }


    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
       stage('trying jenkinsfile') {
                   steps {
                       echo 'This is running from github'
                   }
               }
                stage('Git checkout') {
                                  steps {
                                      git branch: '$BRANCH_NAME', credentialsId: 'Abdullahi_amoo', url: 'https://github.com/IBT-learning/ibt-maven.git'
                                  }
                              }
                stage(' linux command ') {
                                 steps{
                                        sh 'ls -lrt'
                                 }
                              }
                stage('list files') {
                    steps{
                     sh '''
                     ls -lrt
                     pwd
                     who
                     '''
                     }
                     }
                stage('parameter'){
                  steps{
                     sh 'echo $CHOICES'

                  }

                }



                 }
                }





