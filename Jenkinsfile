pipeline {
   agent any
<<<<<<< HEAD
   parameters{
=======
      parameters{
>>>>>>> 63d0d2da4c54fc0a2bd9e6d6d328f64876ae2eb7
        string(name: 'Branch_Name', defaultValue:'main', description:'enter the value to checkout')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
    }
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
                     steps {
                          echo 'testing Jenkins file once more'
                     }
                 }
        stage('Git checkout') {
               steps {
                    checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'IBT-GitHub', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                                            sh 'dir'
                                            sh 'echo $Branch_Name $CHOICES'

                                       }
                                   }






    }
}
