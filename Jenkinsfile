 stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Hi') {
            steps {
                echo 'Hi this is Moses. And this is my first pipeline job.'
            }
        }
        stage('GIT') {
            steps {
                echo 'This is connecting to my repository on github.'
                git branch: 'feature-moses', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }