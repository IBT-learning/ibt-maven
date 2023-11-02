pipeline {
    agent any
    parameters{
       string(name: 'USER_NAME', defaultValue: 'Morel Sami', description: 'User Introduction')
       string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Git target branch')
    }

    stages {
        stage('Greetings') {
            steps {
                echo 'Hello $USER_NAME !!'
            }
        }
        stage('Build job details') {
            steps {
                echo 'Current job details ...'
                echo '$JOB_NAME - $BUILD_NUMBER'
                echo '$JOB_DISPLAY_URL'
            }
        }
        stage('Git checkout') {
            steps {
                echo 'Into new branch $BRANCH_NAME ...'
                git branch: '$BRANCH_NAME', credentialsId: 'smorel_git_account', url: 'https://github.com/IBT-learning/ibt-maven.git'
                sh 'ls -lsrt src'
                sh 'cat src/main/java/com/ibt/app/App.java'
                echo 'all good'
            }
        }
        stage('Maven build job') {
            steps {
                echo 'Starting maven build job to artifactory ...'
                echo 'Oops no configuration found'
                echo 'Will try another time'
            }
        }
    }
}