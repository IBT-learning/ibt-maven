pipeline{
  agent any

  parameters {
  string(name:"Branch_Name", defaultValue: "main", description: "Enter branch to build")
  choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
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
      bat 'dir'
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
             ${params.Branch_Name}=='main'
        }
     }
     steps{
        echo "running on main branch"
     }
   }
  } //stages
} //pipeline
