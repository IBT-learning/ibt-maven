pipeline {
    agent any
    parameters {
        string(name: "Branch_Name", defaultValue: "main", description: "Enter branch to build")
         choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
    }

     environment{
        version = '1.5.4'
      }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        } //stage1 end
        stage('hi') {
            steps {
                echo 'Hello World'
            }
        } //stage2 end
        stage('Download from Git') {
            steps {
                git branch: '$Branch_Name', changelog: false, credentialsId: 'GITHUB_cred_alaskatubbie', poll: false, url: 'https://github.com/Alaskatubbie/nov-cohort.git'
            }
        } //stage3 end
        stage('List files') {
            steps {
                    echo "listing files to verify"
                    bat '''
                        dir
                        cd
                    '''
            }
        } //stage4 end
        stage('list choice'){
            steps{
                echo "Choice: ${params.CHOICES}"
            }
        } //stage5 end
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
        } //stage6 end
        stage('test'){
            steps{
                echo 'testing'
                echo "${env.version}"
                bat 'echo %version%'

            }
        } //stage7 end
    } //stages ending
     post {
              always {
                  echo 'I will always say Hello again!'
              }
          }

} //Pipeline end