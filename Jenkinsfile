pipeline {
    agent any

    parameters{
     string(name: 'BRANCH_NAME', defaultValue: 'staging', description: 'which branch to build on')
     choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose your number')
     }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi this is Chinwe'
            }
        }
        stage('trying jenkinsfile'){
            steps{
                 echo 'this is running from github'
            }
        }
        stage('git checkout'){
             steps{
                  git branch: '$BRANCH_NAME', changelog: false, credentialsId: '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', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }

         stage('list files'){
            steps{
                sh '''
                ls -lrt
                pwd
                who
                '''
            }
        }

        stage('parameter'){
        when{
          expression{
                env.BRANCH_NAME=='main'
          }
        }
            steps{
                sh 'echo $CHOICES'
            }
            }
        }
    }



