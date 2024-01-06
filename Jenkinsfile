pipeline {
    agent any


    parameters {
    string(name:"Branch_name", defaultValue: "main", description:"Enter a branch to build")
    choice(name: 'CHOICES', choices: ['One', 'Two', 'Three'], description: 'Pick a number')
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
        }

        }// stages
} // pipeline