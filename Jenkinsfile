pipeline{
    agent any

    parameters {
      string(name:"Branch_Name", defaultValue: "main", description: "Enter branch to build")
      choice(name: 'CHOICE', choices: ['one', 'two', 'three'], description: 'chose a number')
    }

    environment{
      version = '1.3.0'
    }
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
               git branch: '$Branch_Name', credentialsId: 'GitHub_cred_kayshow04', url: 'https://github.com/IBT-learning/ibt-maven.git'
           }

        } // stage 3
      stage('List files'){
        steps{
          echo "listing files to verify"
         bat 'dir'
        }
      }
      stage('list choice'){
      steps{
          echo "Choice: ${params.CHOICE}"
         }
      }
      stage('run on condition')
      {
     when {
        expression {
           env.BRANCH_NAME =='main'
       }
     }
     steps{
       echo "running on main branch"
     }
    }
    stage('test'){
    steps{
       echo 'testing'
       echo "${env.version}"
        bat 'echo %version%'
     }
    }
  } // stages
}  //pipeline
