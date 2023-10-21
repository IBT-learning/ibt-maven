pipeline{
       agent any

       parameters{
         string (name:'Branch_name' , defaultValue:'main' , description: 'enter the name to build')

       }


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



                                         stage("list all my files"){
                                                 steps{
                                                   git branch:'$Branch_Name', changelog: false, credentialsId: '51d1639f-8a1d-4b1b-a14e-b14153766db4', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'

                                                  }

                                         }

                                           stage("list all my list"){
                                              steps{
                                                sh 'ls -lrt'

                                              }

                                            }

            }

}
