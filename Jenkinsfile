pipeline{
  agent any

  parameters {
  string(name:"Branch_Name", defaultValue: "main", description: "Enter branch to build")
  choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
  }

  environment{
    version = '1.02.08'
  }

  stages{
  stage('Hello'){
  steps{
      echo "hello"
    }
  } // stage 1
  stage('Hi'){
    steps{
      echo "Hi"
    }
   } //stage 2
   stage('Download from git'){
   steps{
         git branch: '$Branch_Name', changelog: false, credentialsId: 'GitHub_cred_Nasirfaizi', poll: false, url: 'https://github.com/Nasirfaizi/nov-cohort.git'
       }
     } //stage 3
     stage('List files'){
 steps{
   echo "listing files to verify"
      sh '''
      dir
      '''
     }
   }
   stage('List choice'){
    steps{
    echo "Choice: ${params.CHOICES}"
    }
   }
   stage('run on condition')
   {
     when {
        expression{
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
       sh 'echo %version%'
       script{
           print env.version
       }
    }
   }
  } //stages
  post {
          always {
              echo 'I will always say Hello again!'
          }
      }
} //pipeline
