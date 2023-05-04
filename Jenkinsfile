pipeline {
   agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('test') {
            steps {
                echo 'test'
            }
        }
         stage('yellow') {
            steps {
                 echo 'yellow'
            }
        }
        stage('testing Jenkins once more') {
        when{
            expression{
              env.BRANCH_NAME=='main'
            }
        }
             steps {
                 echo 'testing Jenkins file once more'
            }
        }
        stage('Git checkout') {
              steps {
                   checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'IBT-GitHub', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                                            sh 'dir'
                                            sh 'echo $Branch_Name $CHOICES'
                                            sh 'echo trying hook'
                                         }
                                   }
                                   stage('testing hooks') {
                                           steps {
                                                echo 'hook tested success'
                                           }
                                       }
                                       stage('testing hook2') {
                                                             steps {
                                                                  echo 'hook tested success'
                                                    }
                                                }









   }
}




