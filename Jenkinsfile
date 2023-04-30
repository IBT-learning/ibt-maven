pipeline {
//@global variable can be used at any stage
    environment{
        version = '1.3.0'
    }
    tools{
        maven 'maven_3.8'
    }
    agent any
//     parameters{
//         string(name: 'Branch_Name', defaultValue: 'main', description: 'Enter the branch to checkout')
//         choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
//     }


    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi'
                echo "${env.version}"  // if env.variable always use evn.variable_name in double quotes
            }
        }
         stage('Hi test') {
            steps {
                echo 'Hi testing Jenkins'
            }
        }
        stage('Jenkinsfile test') {
        when{
            expression{
//                 $Branch_Name=='main'
                env.BRANCHA_NAME=='main'
            }
        }
             steps {
                 echo 'Jenkinsfile test'
                    }
                }
        stage('Git checkout') {
            steps {
//                 checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/$Branch_Name']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                   checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature_anya']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                sh 'ls -lrt'
                sh 'echo $Branch_Name $CHOICES'
            }
        }
         stage('Testing hooks') {
//@local variable - can be used only at this level /stage
          environment{
                 version2 = '1.5.0'
             }
                     steps {
                         echo 'Testing hooks - **SUCCESS**'
                         echo "${env.version2}" // if env.variable always use evn.variable_name in double quotes
                            }
                        }
        }
        stage('mvn version') {
                    steps {
                        sh 'mvn --version'
                    }
        }

  post{
            always{
        //    mail bcc: '', body: 'Testing Jenkins', cc: '', from: '', replyTo: '', subject: 'Testing Jenkins', to: 'annushkaar77@gmail.com'
            echo "*** Build Successful ***"
                }
       }
}
