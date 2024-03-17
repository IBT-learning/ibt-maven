pipeline{
 agent any

 stages{
    stage("hello"){
    steps{
    echo "Hello World!"
    }
   }
    stage("hi"){
        steps{
        echo "hi this is abel"
        }
    }
    stage("Github download"){
        steps{
        git branch: 'jan2024-abelsulamo', credentialsId: 'asulamo24_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'

        }
    }

 }


}
