pipeline{
       agent any

           stages{
              stage("Hello World"){
              steps{
                  echo "Hello World"
              }
           }
            stage("Hello World second script"){
                         steps{
                             echo "Hello World second script"
                         }
                      }
                                  stage("git checkout"){
                                       steps{
                                         git branch: 'feature-rizme', changelog: false, credentialsId: 'GitHub_user_rizme', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'

                                          stage("list all my fills"){
                                             steps{
                                               sh 'ls-lrt'
                                             }

                                          }


                                       }



                                  }



       }

}





