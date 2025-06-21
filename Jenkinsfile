pipeline {
    agent any
    parameters{
     string(name:'Branch-Name', defaultValue:'main', description:'Enter the branch to checkout')
     choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi'
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Testing jenkinsfile') {
        when{
             expression{
                env.BRANCH_NAME=='main'
             }
        }
             steps {
                 echo 'Testing jenkinsfile'
            }
        }
        stage('Git checkout') {
            steps{
                 checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/feature-davido']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-login-credential', url: 'https://github.com/IBT-learning/ibt-maven.git']])
                 bat 'dir'
                 bat 'echo $Branch-Name $CHOICES'
                 bat 'echo trying hook'
            }
        }
        stage('Testing hook') {
            steps{
                 echo 'hook tested success'
            }
        }
    }
}
