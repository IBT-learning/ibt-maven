pipeline {
   environment{
      version= '1.3.0'
      }
   agent any
    stages {
        stage('Hello') {
            steps {
                echo %"{env.version}"%
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
                   checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_sullivan']], extensions: [], userRemoteConfigs: [[credentialsId: 'IBT-GitHub', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                                            sh 'dir'
                                            sh 'echo $Branch_Name $CHOICES'
                                            sh 'echo trying hook'
                                         }
                                   }
                                   stage('testing hooks') {
                                    environment{
                                         version2= '1.5.0'
                                         }
                                           steps {
                                                echo 'hook tested success'
                                                echo %"{env.version}"%
                                           }
                                       }










   }
}




