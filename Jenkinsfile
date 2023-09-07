pipeline{
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'hello world'
            }
        }
        stage ('hi') {
            steps{
                echo 'hi'
            }
        }
        stage ('howdy') {
            steps{
                echo 'howdy'
            }
        }
        stage ('Git'){
            steps {
                git branch: 'feature-Martin2', changelog: false, credentialsId: 'MartinChuks', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('List files'){
            steps{
                bat 'dir'
            }
        }
    }
}
