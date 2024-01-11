pipeline{
  agent { label 'UX-IBT' }

  parameters {
    string(name:"Branch_Name", defaultValue: "main", description: "Enter branch to build")
    choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
  }

  environment{
    version = '1.3.0'
  }

  stages{
    stage('Hello'){
      steps{
        echo "hello"
      }
    } // stage 1
    stage('HI'){
      steps{
        echo "hi"
      }
    } //stage 2
    stage('Download from Git'){
      steps{
           git branch: '$Branch_Name', changelog: false, credentialsId: 'GitHub_cred_gunjan', poll: false, url: 'https://github.com/gunjvm/nov-cohort.git'
        }
    } // stage 3
   stage('List files'){
     steps{
       echo "listing files to verify"
       sh '''
        ls -lrt
        pwd
       '''
     }
   }
   stage('list choice'){
    steps{
        echo "Choice: ${params.CHOICES}"
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
        sh 'echo $version'
        script{
            print env.version
        }
    }
   }
  }  // stages
  post {
          always {
              echo 'I will always say Hello again!'
          }
      }
}  //pipeline
