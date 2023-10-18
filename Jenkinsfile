pipeline {
    agent {label 'UX_IBT'}
    parameters{
        string(name: 'branch_name', defaultValue: 'main', description: 'enter the branch to build')
    }

    environment{
        version = '1.3.2'
    }
    stages{
        stage('Hello') {
            steps{
                echo "hello"
            }
        }
         stage('Git checkout') {
              steps{
                   git branch: '$branch_name', credentialsId: 'mvn_user_credential_github', url: 'https://github.com/IBT-learning/ibt-maven.git'
                   }
                }
                stage('list my files'){
                     when{
                         expression{
                             '$branch_name' == 'main'
                             }
                         }
                    steps{
                        bat 'dir'
                    }
                }
                stage('list environment vers'){
                    steps{
                    bat 'echo "${env.version}" '
                    bat 'echo $version'
                    bat 'dir'
                    script{
                        print env.version

                    }

               }
         }
         stage('checking webook') {
                     steps{
                         echo "from auto run"
                     }
                 }
    }
}