pipeline{
  agent any

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
           git branch: 'main', changelog: false, credentialsId: 'GitHub_cred_gunjan', poll: false, url: 'https://github.com/gunjvm/nov-cohort.git'
        }
    } // stage 3
   stage('List files'){
     steps{
       sh 'ls -lrt'
     }
   }
  }  // stages
}  //pipeline
