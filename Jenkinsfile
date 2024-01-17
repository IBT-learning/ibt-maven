pipeline{
    agent any

    stages {
        stage('Hello'){
            steps {
                echo 'Hello World'
            }
        } // stage 1
         stage('Howdy'){
            steps{
                echo 'Howdy'
            }
        } // stage 2
        stage('Download from Git'){
          steps{
               git branch: 'main', credentialsId: 'GitHub_cred_kayshow04', url: 'https://github.com/IBT-learning/ibt-maven.git'
           }

        } // stage 3
      stage('List files'){
        steps{
          echo "listing files to verify"
         bat '''
           'dir'
           'pwd'
           '''
        }
      }
    } // stages
}   //pipeline
