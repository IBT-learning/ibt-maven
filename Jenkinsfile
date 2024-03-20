pipeline {
 agent any

 parameters {
     string(name: 'Branch_name', defaultValue: 'main', description: 'Enter branch to build')
     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
 }


 stages {
   stage ("hello"){
       steps{
           echo "hello world"
       } //step
    } //stage1
    stage ("hi"){
      steps{
         echo "hi this is olufunmi"
      } //step
    } //stage2
    stage('Github download') {
        steps{
             git branch: '$Branch_name', credentialsId: 'olufunmi11_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
    } //stage3
    stage ("List Repo contents") {
       steps{
           sh 'ls -lrt'
       } //step
    } //stage4
    stage ('print commands') {
    when {
        expression {
             '${params.CHOICE}'=='Two'
        }
    }
       steps {
          echo '$CHOICE'
          echo "Choice: ${params.CHOICE}"
       } //step
    } //stage5
    stage ('Example Deploy'){
       when {
          branch 'main'
       }
        steps{
            echo "Deploying..."
        }
    }
 } // end of stages
} // end of pipeline