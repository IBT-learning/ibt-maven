pipeline {
    agent any

 parameters {
     string(name: 'Branch_name' , defaultValue: 'main' , description: 'Enter branch to  build')
     choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
 }


    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('hi') {
            steps {
                echo 'hi this is anna'
            } //step
        } //stage2
        stage( ' Github download ') {
         steps{
             git branch: '$Branch_name' , credentialsId: 'bagul_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
             }
         }
         stage ('List Repo contents')  {
         steps{
              sh 'ls -lrt'
              }
         }
         stage ('Print commands') {
         steps {
             echo "Choice: ${params.CHOICE}"
             }
             }
           stage ('Example Deploy') {
            when {
              branch 'main'
              }
             steps{
                echoo "Deploying..."
                }
                }
    } //  end of stages
 } //end of pipeline