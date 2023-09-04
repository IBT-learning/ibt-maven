pipeline {
    agent any

    environment {
        version = "1.5"
        db_name = "ibt_db"
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    stage('env variables') {
     steps{
       sh 'echo $version'
       echo "${env.version}"
       echo "${env.db_name}"

       script {
          print env .version
       }

     }
    }
    }

    }