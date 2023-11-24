pipeline {
    agent any
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'branch to build on') }
        parameters {
            choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose your number') }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World, This is femi'
            }
        }
         stage('Howdy!') {
            steps {
                echo 'Welcome everyone to view my pipeline project'
            }
        }
        stage('Trying a new jenkins file') {
            steps {
                echo 'getting used to jenkins pipeline using script'
            }
        }
        stage ('git checkout') {
            steps {
                git branch: '$BRANCH_NAME', changelog: false, credentialsId: 'git_femi', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'

            }
        }
        stage ('list files') {
            steps {
                sh '''
                ls -ltr
                pwd
                who
                '''
            }
        stage ('parameter') {
                    steps {
                       sh 'echo $CHOICES'
                    }

        }
    }
}


