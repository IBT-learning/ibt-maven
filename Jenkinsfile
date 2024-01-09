pipeline {
    agent any


    parameters {
    string(name:"Branch_name", defaultValue: "main", description:"Enter a branch to build")
    choice(name: 'CHOICES', choices: ['One', 'Two', 'Three'], description: 'Pick a number')
    }
    environment{
        version = '1.3.0'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        } // stage 1
        stage('Hi') {
            steps {
                echo 'Hello World'
            }
        }// stage 2
        stage('Download from Git'){
        steps{
            git branch: '$Branch_name', changelog: false, credentialsId: 'GitHub_cred_Tagne', poll: false, url: 'https://github.com/christeukam/nov-cohort.git'
             }
        } // stage 3
        stage('List files'){
                steps{bat 'dir'
             }
        } // stage 4

        stage ('list choice')
        {
         steps{
             echo "Choice: ${params.CHOICES}"
              }
        } // stage 5

         stage ('run on condition')
                {
                 when {
                     expression {
                         env.Branch_name == 'main'
                      }
                      }

                      steps{
                           echo "running on main branch"
                      }
                } // stage 6

         stage ('test')
         {
         steps{
              echo 'testing'
              echo "%{env.version}""
              sh 'echo %version'
               }
         }
        }// stages
} // pipeline