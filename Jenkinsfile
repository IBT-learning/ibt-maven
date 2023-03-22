pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi this is Koby'
                echo 'Let\'s see how this goes'
            }
        }
        stage('Git Checkout') {
            steps {
                echo 'additional print statement'
                git branch: 'feature_koby2', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }
}
