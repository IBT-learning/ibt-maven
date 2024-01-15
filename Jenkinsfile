pipeline{
  agent any

   stages{
     stage('Hello'){
       steps{
        echo 'world'
        }
      } //stage1
stage('Hi'){
       steps{
        echo 'world'
        }
      } //stage2
      stage('special'){
             steps{
              echo 'world'
              }
            } //stage3
            stage('Download from git'){
                         steps{
                          git branch: 'main', credentialsId: 'benny_crnd', url: 'https://github.com/bennydelight/november-cohot.git'
                          }
                        } //stage4
                        stage('list file'){
                                                 steps{
                                                 bat 'dir'
                                                   }
                                                } //stage5
     } //stages
} //pipeline